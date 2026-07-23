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

`sim` is published on crates.io -- install it, then every command on this page works
as written.

### Install the sim command

SIM is one command: `sim`, the bootloader that loads codecs and libraries. Install the batteries-included build below and you get `sim repl`, `sim webui`, and `sim mcp` -- one install, nothing else to add. (Embedders who want only the thin bootloader can `cargo install sim-run` for the separate `sim-run` binary; the `sim` command always comes from `sim-nest`.)

```shell
cargo install sim-nest --features serve-cli   # installs the `sim` command
sim --version
```

[More: sim-sdk](docs/repos/sim-sdk.md)

## Get started -- spin it up

With the binary in hand, start one of SIM's surfaces and poke at it. Each one is
a library the `sim` bootloader loads on demand -- the REPL included: it evaluates
your expression through an eval stack `sim` loads at startup, not a built-in.

### See the Web UI

Spin up the SIM Web-UI shell and open it in a browser -- the cookbook, the Atelier cache view, and the live surface. `sim webui` prints a local URL on startup.

```shell
sim webui
```

[More: sim-web](docs/repos/sim-web.md)

### Run an MCP server

Start a Model Context Protocol server so an MCP client -- an editor, an agent -- can call SIM tools over stdio.

```shell
sim mcp
```

[More: sim-agent-net](docs/repos/sim-agent-net.md)

### Start a REPL

Read-eval-print: pipe or type a Lisp expression and the batteries `sim` evaluates it. The eval stack -- numbers prelude, core runtime, and the Lisp codec -- is linked into the `sim repl` verb, so it works straight from `cargo install sim-nest --features serve-cli` with no extra setup or native dylib bundle.

```shell
sim repl
```

[More: sim-run](docs/repos/sim-run.md)

From here the trail goes deeper: the tour below shows how SIM works under the
hood, the repository catalog lists the whole constellation, and `sim-sdk` is the
developer entry point (its `README.md` quickstart and `DEVELOPING.md`).

## Uninstall

Done trying it? Remove the `sim` command by uninstalling the crate you installed:

```shell
cargo uninstall sim-nest        # the batteries build from Install above
# installed only the thin bootloader instead? -> cargo uninstall sim-run
```

Uninstall by crate name (not the binary name `sim`), and pass no `--features`. If
you are unsure which crate owns `sim`, `cargo install --list` shows it.

The `sim` command caches downloaded library artifacts under `sim/libs` in your
cache directory -- `$SIM_CLI_CACHE_DIR` if you set it, otherwise
`$XDG_CACHE_HOME/sim/libs`, otherwise `~/.cache/sim/libs`. It writes nothing
else outside that cache. To remove the cache too:

```shell
rm -rf "${XDG_CACHE_HOME:-$HOME/.cache}/sim"
```

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

SIM is published: the libraries are on crates.io, and the facade `sim-nest`
(imported as `sim`) pulls the standard distribution together. You can:

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

- **Add it to a project.** `cargo add sim-nest` pulls in the batteries-included
  distribution (imported as `sim`); the `sim` command line is a separate install
  (see Install above).

## The tour -- how it works

A closer look under the hood -- short, runnable examples. Each block is the
published command, with its output captured and verified against the live
workspace.

### One expression, every codec

Decode a Lisp string into the shared expression graph, round-trip it through the JSON and binary codecs, and confirm all three decode back to the identical Expr. Codecs are first-class, reversible objects over one graph.

```shell
cargo add sim-nest --features codec-lisp,codec-json,codec-binary,numbers-prelude
cargo run --example codec_roundtrip
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
- [sim-auto](docs/repos/sim-auto.md)
- [sim-citizen](docs/repos/sim-citizen.md)
- [sim-codecs](docs/repos/sim-codecs.md)
- [sim-construction](docs/repos/sim-construction.md)
- [sim-discrete](docs/repos/sim-discrete.md)
- [sim-femm](docs/repos/sim-femm.md)
- [sim-foundation](docs/repos/sim-foundation.md)
- [sim-kernel](docs/repos/sim-kernel.md)
- [sim-ledger](docs/repos/sim-ledger.md)
- [sim-music](docs/repos/sim-music.md)
- [sim-numbers](docs/repos/sim-numbers.md)
- [sim-office](docs/repos/sim-office.md)
- [sim-run](docs/repos/sim-run.md)
- [sim-runtime](docs/repos/sim-runtime.md)
- [sim-sdk](docs/repos/sim-sdk.md)
- [sim-shape](docs/repos/sim-shape.md)
- [sim-storage](docs/repos/sim-storage.md)
- [sim-stream](docs/repos/sim-stream.md)
- [sim-stream-host](docs/repos/sim-stream-host.md)
- [sim-tooling](docs/repos/sim-tooling.md)
- [sim-web](docs/repos/sim-web.md)

See also: [repository map](docs/site/repos.md), [crate ownership](docs/site/crate-ownership.md), [agent-card catalog](docs/site/agent-card-catalog.md), [SIM Index features](docs/site/index-features.md), [constellation diagram](docs/site/constellation.md).

The SIM Index contributes 92 feature rows and 195 surface rows to this navigation.

The two SIM entry points -- sim-say = this generated public welcome; sim-sdk = the developer entry point and umbrella `sim` crate.

This page is generated from each repository's pinned contract files and is not edited directly.
