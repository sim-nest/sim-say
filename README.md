# SIM -- an expandable Rust runtime

SIM is a small protocol **kernel** surrounded by a large set of loadable
**libraries**. The kernel defines contracts; libraries provide behavior. Almost
everything you would normally bake into a language -- its syntax, its number
types, its evaluator, its codecs, even its standard library -- is a lib you can
add, swap, or remove. The kernel stays small on purpose.

It is a Rust runtime with many *codec surfaces*, not a Lisp. Lisp is one codec
among several (JSON, a binary frame format, an Algol-style infix grammar, and
more); the system identity is the kernel, not any one syntax.

The whole thing runs on one data flow:

```text
tokens  ->  checked forms  ->  objects  ->  checked calls  ->  objects  ->  encoded forms
        decode             build       dispatch          act          encode
```

## Install

Each block below is the command as it will read once SIM is published; the
`# <mockup>` block under it does the **same thing today** from a local
constellation workspace, so you can try everything now and catch bugs.

### Install the sim binary

SIM ships a single `sim` command -- the bootloader that loads codecs and libraries. `sim-run` is the thin bootloader; the batteries-included build (`sim-nest` with `serve-cli`) adds the MCP and Web serve surfaces (`sim mcp`, `sim serve`) without a separate wrapper install.

```shell
cargo install sim-run                          # the thin sim bootloader
cargo install sim-nest --features serve-cli    # sim + mcp/web serve surfaces
sim --version
```
```shell
# <mockup>
cargo run --manifest-path .meta-workspace/Cargo.toml -p sim-run --bin sim -- --version
```

[More: sim-sdk](docs/repos/sim-sdk.md)

## Get started -- spin it up

With the binary in hand, start one of SIM's surfaces and poke at it. Each one is
a library the `sim` bootloader loads on demand -- the REPL included: it evaluates
your expression through an eval stack `sim` loads at startup, not a built-in.

### See the Web UI

Spin up the SIM Web-UI shell and open it in a browser -- the cookbook, the Atelier cache view, and the live surface.

```shell
sim webui
```
```shell
# <mockup>
cargo run --manifest-path .meta-workspace/Cargo.toml -p sim-web-shell
# then open the URL it prints on startup
```

[More: sim-web](docs/repos/sim-web.md)

### Run an MCP server

Start a Model Context Protocol server so an MCP client -- an editor, an agent -- can call SIM tools over stdio.

```shell
sim serve mcp
```
```shell
# <mockup>
cargo run --manifest-path .meta-workspace/Cargo.toml -p sim-mcp-server
```

[More: sim-agent-net](docs/repos/sim-agent-net.md)

### Start a REPL

Read-eval-print: pipe or type a Lisp expression and SIM evaluates it through the `sim` bootloader loading the REPL as a library.

```shell
sim repl
```
```shell
# <mockup>
cargo build --manifest-path .meta-workspace/Cargo.toml -p sim-lib-numbers-f64 --features native-export
cargo build --manifest-path .meta-workspace/Cargo.toml -p sim-lib-standard-core --features native-export
printf '(math/add (math/mul 6 7) 0)\n' | cargo run --manifest-path .meta-workspace/Cargo.toml -p sim-run --features dynamic-native --bin sim -- repl
```

[More: sim-run](docs/repos/sim-run.md)

From here the trail goes deeper: the tour below shows how SIM works under the
hood, the repository catalog lists the whole constellation, and `sim-sdk` is the
developer entry point (its `README.md` quickstart and `DEVELOPING.md`).

## Why it is interesting

- **One kernel, many libraries.** Behavior lives in libs loaded at runtime, so
  the system expands without growing its trusted core.
- **One match engine.** Parsing, type checking, dispatch, macro syntax, codec
  grammar, and overload selection all run through a single `Shape` protocol --
  not five parallel implementations.
- **Codecs are first-class, reversible objects.** A decoder turns bytes or text
  into the shared expression graph; an encoder turns it back. General codecs
  round-trip every expression; domain codecs round-trip only their domain and
  fail closed outside it.
- **Location-transparent evaluation.** Code targets a `realize` call on an
  `EvalFabric`, so the same program runs in-process, across a server, or on a
  remote device without rewriting it to a transport.
- **The view/edit surface is just a codec pointed at a device.** A view is an
  encoder; an edit is the matching reversible decoder; a screen session is a
  `realize` target. CLI, web, and watch surfaces are libs, not subsystems.
- **Wasm is a first-class plugin ABI**, so untrusted behavior can be loaded
  under capability and resource limits.

## What you can look at right now

SIM is pre-publish: the libraries are not on crates.io yet, so the
build-and-run path is still being prepared (see the publishing plan). Today you
can:

- **Read the architecture.** Start with the developer overview and the
  machine-checked architecture contract in `sim-sdk` (its `README.md` and
  `SIM.md`).
- **Browse the constellation.** Every repository has a generated page with its
  crates, contracts, and agent cards -- see the repository catalog at the bottom
  of this page.
- **Read the code and its docs.** Each repo ships its own `rustdoc` and
  `recipes/`; the kernel and the codec layer are good places to start.
- **Build the kernel.** `sim-kernel` builds and tests from a lone clone today
  (`cargo test` in a fresh checkout) -- it is the dependency root. The rest of the
  constellation builds together as a workspace; see `sim-sdk`'s `DEVELOPING.md`.

Once the first libraries publish, this section graduates to a one-line
`cargo add sim` plus a runnable `sim` command. That step is tracked and gated;
it is not faked here.

## The tour -- how it works

A closer look under the hood -- short, runnable examples. Each block is the
published command; the `# <mockup>` block under it runs the same thing today from
the workspace, with its output captured and verified.

### One expression, every codec

Decode a Lisp string into the shared expression graph, round-trip it through the JSON and binary codecs, and confirm all three decode back to the identical Expr. Codecs are first-class, reversible objects over one graph.

```shell
cargo add sim --features codec-lisp,codec-json,codec-binary,numbers-prelude
cargo run --example codec_roundtrip
```
```shell
# <mockup>
cargo run --manifest-path .meta-workspace/Cargo.toml -p sim --example codec_roundtrip --features core,shape,codec-lisp,codec-json,codec-binary,numbers-prelude
```
```text
lisp source : (+ 1 2)
as json     : {"$expr":"list","items":[{"$expr":"symbol","name":"+"},{"$expr":"number","domain":"numbers/i64","value":"1"},{"$expr":"number","domain":"numbers/i64","value":"2"}]}
decoded back identical across lisp / json / binary: true
```

[More: sim-codecs](docs/repos/sim-codecs.md)

### What else is in SIM

The tour above is a taste; here is the whole constellation, each area linking its
generated repository page:

| Area | Repos | What it is |
| --- | --- | --- |
| Kernel and protocol boundary | [sim-kernel](docs/repos/sim-kernel.md) | Small contracts -- no hardwired parser, number domain, transport, or standard library baked in. |
| One match engine | [sim-shape](docs/repos/sim-shape.md) | A single `Shape` engine for parsing, checking, binding, dispatch, macro syntax, and projection ranking. |
| Codecs and round-trip | [sim-codecs](docs/repos/sim-codecs.md) | Lisp, JSON, Algol-style, binary, chat, MCP, and a wasm ABI -- reversible objects over one expression graph. |
| Runtime, libraries, and the CLI | [sim-runtime](docs/repos/sim-runtime.md), [sim-sdk](docs/repos/sim-sdk.md), [sim-run](docs/repos/sim-run.md) | Behavior is loadable libraries; the SDK is the developer entry; the CLI is a bootloader that loads codecs and libs. |
| Values, records, and citizens | [sim-foundation](docs/repos/sim-foundation.md), [sim-citizen](docs/repos/sim-citizen.md) | Values, tables, macros, net contracts, surface cards, and the citizen conformance layer. |
| Numbers and discrete math | [sim-numbers](docs/repos/sim-numbers.md), [sim-discrete](docs/repos/sim-discrete.md), [sim-femm](docs/repos/sim-femm.md) | Pluggable number domains, tensors, a CAS, exact/discrete tools, and a 2D finite-element domain. |
| Storage and streams | [sim-storage](docs/repos/sim-storage.md), [sim-stream](docs/repos/sim-stream.md), [sim-stream-host](docs/repos/sim-stream-host.md) | Stored objects, stream graphs, and placement-transparent host execution. |
| Music and audio | [sim-music](docs/repos/sim-music.md), [sim-audio-daw](docs/repos/sim-audio-daw.md) | MIDI, pitch and chord theory, transforms, synthesis, and a DAW/audio-graph stack. |
| Agents and server routes | [sim-agent-net](docs/repos/sim-agent-net.md) | Agent cards, a server fabric, OpenAI-compatible routes, MCP, and tool flows. |
| View/edit surfaces | [sim-web](docs/repos/sim-web.md) | A view is a codec at the `surface` position; an edit is its reversible decoder; host surfaces are loaded. |
| Tooling and browseability | [sim-tooling](docs/repos/sim-tooling.md) | Generated contracts, the agent-card catalog, the browsable doc-site, and Atelier indexes. |

## Where to go next

- **I want to write code against SIM** -> go to **`sim-sdk`**: add the umbrella
  `sim` crate, pick a feature set, boot a runtime in a few lines, and run the
  conformance suite. Its `README.md` is the quickstart and `DEVELOPING.md` is the
  honest current build guide.
- **I want the full repository and contract catalog** -> see below.

SIM is a developer-facing system aimed at people curious about language
runtimes, codecs, and protocol design. You do not need to be one to read on, but
the rewards are highest if you like building the machinery under languages.

## License

SIM is licensed under MPL-2.0. The full text ships as `LICENSE` in this
repository and in each code repository.

## Repository catalog

The full constellation, generated from each repo's pinned contract files:

- [sim-agent-net](docs/repos/sim-agent-net.md)
- [sim-audio-daw](docs/repos/sim-audio-daw.md)
- [sim-citizen](docs/repos/sim-citizen.md)
- [sim-codecs](docs/repos/sim-codecs.md)
- [sim-discrete](docs/repos/sim-discrete.md)
- [sim-femm](docs/repos/sim-femm.md)
- [sim-foundation](docs/repos/sim-foundation.md)
- [sim-kernel](docs/repos/sim-kernel.md)
- [sim-music](docs/repos/sim-music.md)
- [sim-numbers](docs/repos/sim-numbers.md)
- [sim-run](docs/repos/sim-run.md)
- [sim-runtime](docs/repos/sim-runtime.md)
- [sim-sdk](docs/repos/sim-sdk.md)
- [sim-shape](docs/repos/sim-shape.md)
- [sim-storage](docs/repos/sim-storage.md)
- [sim-stream](docs/repos/sim-stream.md)
- [sim-stream-host](docs/repos/sim-stream-host.md)
- [sim-tooling](docs/repos/sim-tooling.md)
- [sim-web](docs/repos/sim-web.md)

See also: [repository map](docs/site/repos.md), [crate ownership](docs/site/crate-ownership.md), [agent-card catalog](docs/site/agent-card-catalog.md), [constellation diagram](docs/site/constellation.md).

The two SIM entry points -- sim-say = this generated public welcome; sim-sdk = the developer entry point and umbrella `sim` crate.

This page is generated from each repository's pinned contract files and is not edited directly.
