# SIM Index Features

Generated from `docs/index/index.cards.jsonl`.

| Feature | Subject | Index page | Specimens | Summary |
| --- | --- | --- | ---: | --- |
| `feature/sim-agent-net/agent-server-tools` | `local/sim-agent-net/crate/sim-lib-server` | [features/feature--sim-agent-net--agent-server-tools.md](../index/features/feature--sim-agent-net--agent-server-tools.md) | 0 | Expose agent-facing server, skill, and OpenAI gateway libraries for model-connected hosts. |
| `feature/sim-agent-net/bridge-runtime` | `crate/sim-lib-agent` | [features/feature--sim-agent-net--bridge-runtime.md](../index/features/feature--sim-agent-net--bridge-runtime.md) | 0 | Transmit, receive, check, and route symmetric human-model packets with agent and bridge runtime support. |
| `feature/sim-agent-net/eval-fabric-sites` | `crate/sim-lib-agent-runner-local` | [features/feature--sim-agent-net--eval-fabric-sites.md](../index/features/feature--sim-agent-net--eval-fabric-sites.md) | 0 | Place model and stream work through loadable runner, local model, and content-addressed fleet libraries. |
| `feature/sim-agent-net/fabric-fixture-cli` | `crate/sim-lib-stream-fabric` | [features/feature--sim-agent-net--fabric-fixture-cli.md](../index/features/feature--sim-agent-net--fabric-fixture-cli.md) | 0 | Replay content-addressed stream-fabric fixtures through the loadable fixture command. |
| `feature/sim-agent-net/forge-intent` | `local/sim-agent-net/crate/sim-lib-forge` | [features/feature--sim-agent-net--forge-intent.md](../index/features/feature--sim-agent-net--forge-intent.md) | 0 | Compile high-level intent records into checked Forge output through the loadable Forge runtime library. |
| `feature/sim-agent-net/generated-docs` | `local/sim-agent-net/crate/xtask` | [features/feature--sim-agent-net--generated-docs.md](../index/features/feature--sim-agent-net--generated-docs.md) | 0 | Publish generated package, card, recipe, and index facts for agent, bridge, MCP, and fabric crates. |
| `feature/sim-agent-net/mcp-server` | `local/sim-agent-net/crate/sim-lib-mcp` | [features/feature--sim-agent-net--mcp-server.md](../index/features/feature--sim-agent-net--mcp-server.md) | 0 | Serve MCP requests through the loaded sim-lib-mcp command and runtime libraries. |
| `feature/sim-agent-net/output-contract-repair-cli` | `crate/sim-lib-agent-runner-core-recipe-output-contract-repair` | [features/feature--sim-agent-net--output-contract-repair-cli.md](../index/features/feature--sim-agent-net--output-contract-repair-cli.md) | 0 | Repair model output contracts with the checked runner-core fixture command. |
| `feature/sim-audio-daw/audio-device-providers` | `crate/sim-lib-stream-cpal` | [features/feature--sim-audio-daw--audio-device-providers.md](../index/features/feature--sim-audio-daw--audio-device-providers.md) | 0 | Model host audio devices and load JACK, cpal, PipeWire, ALSA, ASIO, CoreAudio, and PortAudio provider paths. |
| `feature/sim-audio-daw/audio-graph-workbench` | `local/sim-audio-daw/crate/sim-lib-audio-graph-core` | [features/feature--sim-audio-daw--audio-graph-workbench.md](../index/features/feature--sim-audio-daw--audio-graph-workbench.md) | 0 | Compose offline and live audio graph descriptors with DSP and gain-plugin examples. |
| `feature/sim-audio-daw/generated-docs` | `local/sim-audio-daw/crate/xtask` | [features/feature--sim-audio-daw--generated-docs.md](../index/features/feature--sim-audio-daw--generated-docs.md) | 0 | Publish generated package, card, recipe, and index facts for the audio and plugin crates. |
| `feature/sim-citizen/citizen-read-constructs` | `crate/sim-citizen` | [features/feature--sim-citizen--citizen-read-constructs.md](../index/features/feature--sim-citizen--citizen-read-constructs.md) | 1 | Expose Rust values as runtime citizens with class members, registry rows, and read-construct round trips. |
| `feature/sim-codecs/bridge-packet-codec` | `crate/sim-codec-bridge` | [features/feature--sim-codecs--bridge-packet-codec.md](../index/features/feature--sim-codecs--bridge-packet-codec.md) | 1 | Encode and decode Bridge packet workflow data through the Bridge wire grammar. |
| `feature/sim-codecs/codec` | `crate/sim-codec` | [features/feature--sim-codecs--codec.md](../index/features/feature--sim-codecs--codec.md) | 0 | Define codec positions, limits, syntax surfaces, wire surfaces, and loadable codec runtime libraries. |
| `feature/sim-codecs/contract-emitter` | `local/sim-codecs/crate/xtask` | [features/feature--sim-codecs--contract-emitter.md](../index/features/feature--sim-codecs--contract-emitter.md) | 0 | Emit generated repository contract and index fragments for codec crates. |
| `feature/sim-codecs/domain-syntax-grammars` | `crate/sim-codec` | [features/feature--sim-codecs--domain-syntax-grammars.md](../index/features/feature--sim-codecs--domain-syntax-grammars.md) | 0 | Read and write binary, bitwise, chat, config, document, index, and MCP grammar surfaces. |
| `feature/sim-codecs/expression-syntax-grammars` | `crate/sim-codec-lisp` | [features/feature--sim-codecs--expression-syntax-grammars.md](../index/features/feature--sim-codecs--expression-syntax-grammars.md) | 0 | Read and write Lisp, JSON, Algol, Lua, Compare, and Bridge rendered expression grammars. |
| `feature/sim-codecs/pratt` | `crate/sim-codec-pratt` | [features/feature--sim-codecs--pratt.md](../index/features/feature--sim-codecs--pratt.md) | 0 | Parse operator-oriented expression languages through the Pratt codec surface. |
| `feature/sim-codecs/wire-protocol-grammars` | `crate/sim-codec` | [features/feature--sim-codecs--wire-protocol-grammars.md](../index/features/feature--sim-codecs--wire-protocol-grammars.md) | 0 | Read and write binary, bitwise, chat, config, document, index, and MCP wire protocols. |
| `feature/sim-foundation/contract-emitter` | `local/sim-foundation/crate/xtask` | [features/feature--sim-foundation--contract-emitter.md](../index/features/feature--sim-foundation--contract-emitter.md) | 0 | Emit generated repository contract and index fragments for foundation crates. |
| `feature/sim-foundation/cookbook` | `crate/sim-cookbook` | [features/feature--sim-foundation--cookbook.md](../index/features/feature--sim-foundation--cookbook.md) | 0 | Describe reusable recipe metadata and generated cookbook records consumed by public docs and tooling. |
| `feature/sim-foundation/host-primitives` | `crate/sim-lib-net-core` | [features/feature--sim-foundation--host-primitives.md](../index/features/feature--sim-foundation--host-primitives.md) | 0 | Provide shared network and surface-card helper crates for host-facing runtime libraries. |
| `feature/sim-foundation/index-graph-core` | `crate/sim-index-core` | [features/feature--sim-foundation--index-graph-core.md](../index/features/feature--sim-foundation--index-graph-core.md) | 0 | Define canonical SIM Index records, ids, edges, checks, and card projections for tooling and codecs. |
| `feature/sim-foundation/library-macros` | `crate/sim-macros` | [features/feature--sim-foundation--library-macros.md](../index/features/feature--sim-foundation--library-macros.md) | 0 | Generate checked Rust declarations for authored SIM libraries and codec markers. |
| `feature/sim-foundation/table-dir-core` | `crate/sim-table-core` | [features/feature--sim-foundation--table-dir-core.md](../index/features/feature--sim-foundation--table-dir-core.md) | 0 | Define shared table and directory contracts used by storage, index, and host-facing libraries. |
| `feature/sim-foundation/value-helpers` | `crate/sim-value` | [features/feature--sim-foundation--value-helpers.md](../index/features/feature--sim-foundation--value-helpers.md) | 0 | Provide shared value conversion and table-field helpers for reusable runtime libraries. |
| `feature/sim-kernel/contract-emitter` | `local/sim-kernel/crate/xtask` | [features/feature--sim-kernel--contract-emitter.md](../index/features/feature--sim-kernel--contract-emitter.md) | 0 | Emit generated repository contract and index fragments for the kernel crate. |
| `feature/sim-kernel/kernel-contracts` | `crate/sim-kernel` | [features/feature--sim-kernel--kernel-contracts.md](../index/features/feature--sim-kernel--kernel-contracts.md) | 0 | Define the protocol kernel for values, context, registries, shapes, capabilities, and export records. |
| `feature/sim-ledger/generated-docs` | `local/sim-ledger/crate/xtask` | [features/feature--sim-ledger--generated-docs.md](../index/features/feature--sim-ledger--generated-docs.md) | 0 | Publish generated package, card, recipe, and index facts for the ledger crates. |
| `feature/sim-ledger/ledger-command` | `crate/sim-ledger-cli` | [features/feature--sim-ledger--ledger-command.md](../index/features/feature--sim-ledger--ledger-command.md) | 0 | Run ledger import, drafting, trial balance, and closing flows through the checked command package. |
| `feature/sim-ledger/ledger-libraries` | `crate/sim-ledger` | [features/feature--sim-ledger--ledger-libraries.md](../index/features/feature--sim-ledger--ledger-libraries.md) | 0 | Provide voucher storage, book construction, and closing libraries for ledger workflows. |
| `feature/sim-music/generated-docs` | `local/sim-music/crate/xtask` | [features/feature--sim-music--generated-docs.md](../index/features/feature--sim-music--generated-docs.md) | 0 | Publish generated package, card, recipe, and index facts for the music, MIDI, pitch, and sound crates. |
| `feature/sim-music/midi-notation-workflows` | `crate/sim-lib-midi-core` | [features/feature--sim-music--midi-notation-workflows.md](../index/features/feature--sim-music--midi-notation-workflows.md) | 0 | Lift, lower, inspect, and export musical material across MIDI files, live MIDI fixtures, and notation forms. |
| `feature/sim-music/pitch-and-sound-vocabulary` | `crate/sim-lib-pitch-core` | [features/feature--sim-music--pitch-and-sound-vocabulary.md](../index/features/feature--sim-music--pitch-and-sound-vocabulary.md) | 0 | Name chords, scales, pitch sets, timbres, spectra, and tuning facts through worked musical descriptors. |
| `feature/sim-music/synth-performance-workbench` | `local/sim-music/crate/sim-lib-music-synth` | [features/feature--sim-music--synth-performance-workbench.md](../index/features/feature--sim-music--synth-performance-workbench.md) | 0 | Describe synth presets, streaming render fixtures, and placement choices for local or browser-backed performance. |
| `feature/sim-numbers/numbers` | `crate/sim-lib-numbers-core` | [features/feature--sim-numbers--numbers.md](../index/features/feature--sim-numbers--numbers.md) | 1 | Provide arithmetic, exact, floating, symbolic, tensor, and statistics number domains as loadable libraries. |
| `feature/sim-office/document-codecs` | `crate/sim-lib-office-pack` | [features/feature--sim-office--document-codecs.md](../index/features/feature--sim-office--document-codecs.md) | 0 | Round-trip OOXML, ODF, MSPDI, deck, sheet, and markup documents through office codec recipes. |
| `feature/sim-office/document-surfaces` | `crate/sim-lib-doc-surface` | [features/feature--sim-office--document-surfaces.md](../index/features/feature--sim-office--document-surfaces.md) | 0 | Project document, markup, and suite descriptors into view surfaces for review and editing. |
| `feature/sim-office/generated-docs` | `local/sim-office/crate/xtask` | [features/feature--sim-office--generated-docs.md](../index/features/feature--sim-office--generated-docs.md) | 0 | Publish generated package, card, recipe, and index facts for office documents, sites, and codecs. |
| `feature/sim-office/office-site-workflows` | `crate/sim-lib-doc-site` | [features/feature--sim-office--office-site-workflows.md](../index/features/feature--sim-office--office-site-workflows.md) | 0 | Model document stores, mail and calendar summaries, planning data, and enterprise site reads. |
| `feature/sim-run/bootloader` | `crate/sim-run-core` | [features/feature--sim-run--bootloader.md](../index/features/feature--sim-run--bootloader.md) | 2 | Start product commands through the shared bootloader and loaded runtime libraries. |
| `feature/sim-run/glasses` | `crate/sim-run` | [features/feature--sim-run--glasses.md](../index/features/feature--sim-run--glasses.md) | 0 | Start modeled or hardware-backed glasses plans through the shared command bootloader. |
| `feature/sim-run/index` | `local/sim-run/crate/xtask` | [features/feature--sim-run--index.md](../index/features/feature--sim-run--index.md) | 1 | Expose generated package, card, surface, and recipe facts as a checked SIM Index fragment. |
| `feature/sim-run/index-table-dir` | `crate/sim-lib-index` | [features/feature--sim-run--index-table-dir.md](../index/features/feature--sim-run--index-table-dir.md) | 0 | Expose the embedded SIM Index as immutable Table/Dir collections for loaded runtime code. |
| `feature/sim-run/loaders` | `crate/sim-run-loaders` | [features/feature--sim-run--loaders.md](../index/features/feature--sim-run--loaders.md) | 0 | Load native, source, and re-exported runtime libraries as bootloader inputs. |
| `feature/sim-run/repl` | `crate/sim-lib-repl` | [features/feature--sim-run--repl.md](../index/features/feature--sim-run--repl.md) | 1 | Run a SIM read-eval-print loop through the loaded REPL library and command surface. |
| `feature/sim-run/runtime-index` | `crate/sim-lib-index` | [features/feature--sim-run--runtime-index.md](../index/features/feature--sim-run--runtime-index.md) | 4 | Explore the merged SIM Index through the bootloader as stable Table/Dir rows and structured query output. |
| `feature/sim-run/terminal-surface` | `crate/sim-view-tty` | [features/feature--sim-run--terminal-surface.md](../index/features/feature--sim-run--terminal-surface.md) | 1 | Render and interpret terminal view intents through the loaded TTY surface library. |
| `feature/sim-run/watch` | `crate/sim-run` | [features/feature--sim-run--watch.md](../index/features/feature--sim-run--watch.md) | 0 | Start modeled, imported, or live watch plans through the shared command bootloader. |
| `feature/sim-runtime/capabilities-read-eval` | `crate/sim-lib-core` | [features/feature--sim-runtime--capabilities-read-eval.md](../index/features/feature--sim-runtime--capabilities-read-eval.md) | 1 | Gate diminished read-eval and surface packing through explicit runtime libraries and capability checks. |
| `feature/sim-runtime/contract-emitter` | `local/sim-runtime/crate/xtask` | [features/feature--sim-runtime--contract-emitter.md](../index/features/feature--sim-runtime--contract-emitter.md) | 0 | Emit generated repository contract and index fragments for runtime crates. |
| `feature/sim-runtime/host-exec` | `crate/sim-lib-exec` | [features/feature--sim-runtime--host-exec.md](../index/features/feature--sim-runtime--host-exec.md) | 0 | Expose bounded process execution as a capability-gated host primitive outside the kernel. |
| `feature/sim-runtime/library-loading` | `local/sim-runtime/crate/sim-lib-standard-core` | [features/feature--sim-runtime--library-loading.md](../index/features/feature--sim-runtime--library-loading.md) | 1 | Load standard and language-profile runtime libraries through stable export records. |
| `feature/sim-runtime/organs` | `crate/sim-lib-binding` | [features/feature--sim-runtime--organs.md](../index/features/feature--sim-runtime--organs.md) | 0 | Provide binding, control, logic, pattern, mutation, and sequence organs as loadable runtime libraries. |
| `feature/sim-sdk/conformance-contract` | `crate/sim-conformance` | [features/feature--sim-sdk--conformance-contract.md](../index/features/feature--sim-sdk--conformance-contract.md) | 0 | Run the SDK conformance contract as a checked operational recipe. |
| `feature/sim-sdk/device-recipes` | `crate/sim-nest` | [features/feature--sim-sdk--device-recipes.md](../index/features/feature--sim-sdk--device-recipes.md) | 0 | Exercise modeled device, watch, and glasses workflows through SDK-level recipe entry points. |
| `feature/sim-sdk/facade-codecs` | `crate/sim-nest` | [features/feature--sim-sdk--facade-codecs.md](../index/features/feature--sim-sdk--facade-codecs.md) | 0 | Expose public codec exports through the SDK facade while implementation crates keep the codec behavior. |
| `feature/sim-sdk/facade-model-workflows` | `crate/sim-nest` | [features/feature--sim-sdk--facade-model-workflows.md](../index/features/feature--sim-sdk--facade-model-workflows.md) | 0 | Expose model-facing facade exports for answer routing and drafter setup. |
| `feature/sim-sdk/facade-runtime` | `crate/sim-nest` | [features/feature--sim-sdk--facade-runtime.md](../index/features/feature--sim-sdk--facade-runtime.md) | 0 | Boot the public SIM facade and expose its command plus reversible view surface. |
| `feature/sim-sdk/facade-shapes` | `crate/sim-nest` | [features/feature--sim-sdk--facade-shapes.md](../index/features/feature--sim-sdk--facade-shapes.md) | 0 | Expose public Shape exports through the SDK facade while shape crates keep the matching behavior. |
| `feature/sim-sdk/generated-docs` | `local/sim-sdk/crate/xtask` | [features/feature--sim-sdk--generated-docs.md](../index/features/feature--sim-sdk--generated-docs.md) | 0 | Publish generated package, card, recipe, and index facts for the SDK facade and conformance crate. |
| `feature/sim-shape/contract-emitter` | `local/sim-shape/crate/xtask` | [features/feature--sim-shape--contract-emitter.md](../index/features/feature--sim-shape--contract-emitter.md) | 0 | Emit generated repository contract and index fragments for Shape crates. |
| `feature/sim-shape/shape` | `local/sim-shape/crate/sim-shape` | [features/feature--sim-shape--shape.md](../index/features/feature--sim-shape--shape.md) | 1 | Define reusable Shape matching, binding, citizen projection, and grammar contracts for runtime values. |
| `feature/sim-shape/shape-recipes` | `crate/sim-shape-recipe-exact-bool-shape` | [features/feature--sim-shape--shape-recipes.md](../index/features/feature--sim-shape--shape-recipes.md) | 0 | Carry runnable Shape recipe crates used as checked examples for exact booleans and grammar contracts. |
| `feature/sim-storage/contract-emitter` | `local/sim-storage/crate/xtask` | [features/feature--sim-storage--contract-emitter.md](../index/features/feature--sim-storage--contract-emitter.md) | 0 | Emit generated repository contract and index fragments for storage crates. |
| `feature/sim-storage/host-storage-primitives` | `local/sim-storage/crate/sim-table-fs` | [features/feature--sim-storage--host-storage-primitives.md](../index/features/feature--sim-storage--host-storage-primitives.md) | 0 | Connect file, database, and HTTP storage crates to the shared Table and Dir backend shape. |
| `feature/sim-storage/table-dir-backends` | `local/sim-storage/crate/sim-table-hash` | [features/feature--sim-storage--table-dir-backends.md](../index/features/feature--sim-storage--table-dir-backends.md) | 1 | Provide hash, lazy, override, and list-backed Table/Dir implementations for reusable storage libraries. |
| `feature/sim-stream/stream-protocol-helpers` | `local/sim-stream/crate/sim-lib-stream-core` | [features/feature--sim-stream--stream-protocol-helpers.md](../index/features/feature--sim-stream--stream-protocol-helpers.md) | 1 | Provide rank, topology, stream core, device, wrist, and XR helpers as loadable stream libraries. |
| `feature/sim-tooling/generated-docs` | `local/sim-tooling/crate/xtask` | [features/feature--sim-tooling--generated-docs.md](../index/features/feature--sim-tooling--generated-docs.md) | 0 | Generate repo contracts, feature maps, card indexes, and index fragments through xtask. |
| `feature/sim-web/daw-view-surfaces` | `crate/sim-lib-view-daw` | [features/feature--sim-web--daw-view-surfaces.md](../index/features/feature--sim-web--daw-view-surfaces.md) | 0 | Expose synth, stream, placement, and component views through the DAW view library. |
| `feature/sim-web/device-surfaces` | `local/sim-web/crate/sim-lib-view` | [features/feature--sim-web--device-surfaces.md](../index/features/feature--sim-web--device-surfaces.md) | 0 | Rank and project view surfaces against desktop, phone, watch, and glasses device profiles. |
| `feature/sim-web/generated-docs` | `local/sim-web/crate/xtask` | [features/feature--sim-web--generated-docs.md](../index/features/feature--sim-web--generated-docs.md) | 0 | Publish generated package, card, recipe, and index facts for browser and view crates. |
| `feature/sim-web/view-surface` | `local/sim-web/crate/sim-lib-view` | [features/feature--sim-web--view-surface.md](../index/features/feature--sim-web--view-surface.md) | 0 | Expose view and edit surfaces so codecs, browser hosts, and device profiles can render and reverse surface data. |
| `feature/sim-web/web-shell-host` | `crate/sim-web-shell` | [features/feature--sim-web--web-shell-host.md](../index/features/feature--sim-web--web-shell-host.md) | 0 | Serve browser-facing surfaces through loaded web shell runtime libraries and command entry points. |

## Surface Rows

| Surface | Kind | Subject |
| --- | --- | --- |
| `cli/atelier` | `cli` | `crate/sim-web-shell` |
| `cli/browse` | `cli` | `crate/sim-web-shell` |
| `cli/citizen-roundtrip` | `cli` | `crate/citizen-roundtrip` |
| `cli/glasses` | `cli` | `crate/sim-run` |
| `cli/index` | `cli` | `crate/sim-lib-index` |
| `cli/mcp` | `cli` | `local/sim-agent-net/crate/sim-lib-mcp` |
| `cli/repl` | `cli` | `crate/sim-lib-repl` |
| `cli/serve` | `cli` | `crate/sim-web-shell` |
| `cli/sim-codec-compare` | `cli` | `crate/sim-codec-compare` |
| `cli/sim-fabric-cadr-fixture` | `cli` | `crate/sim-lib-stream-fabric` |
| `cli/sim-ledger-cli` | `cli` | `crate/sim-ledger-cli` |
| `cli/sim-lib-agent-runner-core-recipe-output-contract-repair` | `cli` | `crate/sim-lib-agent-runner-core-recipe-output-contract-repair` |
| `cli/sim-lib-stream-fabric` | `cli` | `crate/sim-lib-stream-fabric` |
| `cli/sim-mcp-server` | `cli` | `crate/sim-mcp-server` |
| `cli/sim-nest` | `cli` | `crate/sim-nest` |
| `cli/sim-run` | `cli` | `crate/sim-run` |
| `cli/sim-shape-recipe-exact-bool-shape` | `cli` | `crate/sim-shape-recipe-exact-bool-shape` |
| `cli/sim-shape-recipe-shape-grammar-contract` | `cli` | `crate/sim-shape-recipe-shape-grammar-contract` |
| `cli/sim-web-shell` | `cli` | `crate/sim-web-shell` |
| `cli/watch` | `cli` | `crate/sim-run` |
| `docs/sim-agent-net/generated` | `docs` | `doc-set/sim-agent-net/generated` |
| `docs/sim-audio-daw/generated` | `docs` | `doc-set/sim-audio-daw/generated` |
| `docs/sim-citizen/generated` | `docs` | `doc-set/sim-citizen/generated` |
| `docs/sim-codecs/generated` | `docs` | `doc-set/sim-codecs/generated` |
| `docs/sim-foundation/generated` | `docs` | `doc-set/sim-foundation/generated` |
| `docs/sim-kernel/generated` | `docs` | `doc-set/sim-kernel/generated` |
| `docs/sim-ledger/generated` | `docs` | `doc-set/sim-ledger/generated` |
| `docs/sim-music/generated` | `docs` | `doc-set/sim-music/generated` |
| `docs/sim-numbers/generated` | `docs` | `doc-set/sim-numbers/generated` |
| `docs/sim-office/generated` | `docs` | `doc-set/sim-office/generated` |
| `docs/sim-run/generated` | `docs` | `doc-set/sim-run/generated` |
| `docs/sim-runtime/generated` | `docs` | `doc-set/sim-runtime/generated` |
| `docs/sim-sdk/generated` | `docs` | `doc-set/sim-sdk/generated` |
| `docs/sim-shape/generated` | `docs` | `doc-set/sim-shape/generated` |
| `docs/sim-storage/generated` | `docs` | `doc-set/sim-storage/generated` |
| `docs/sim-stream/generated` | `docs` | `doc-set/sim-stream/generated` |
| `docs/sim-tooling/generated` | `docs` | `doc-set/sim-tooling/generated` |
| `docs/sim-web/generated` | `docs` | `doc-set/sim-web/generated` |
| `local/sim-agent-net/cli/xtask` | `cli` | `local/sim-agent-net/crate/xtask` |
| `local/sim-audio-daw/cli/xtask` | `cli` | `local/sim-audio-daw/crate/xtask` |
| `local/sim-citizen/cli/xtask` | `cli` | `local/sim-citizen/crate/xtask` |
| `local/sim-codecs/cli/xtask` | `cli` | `local/sim-codecs/crate/xtask` |
| `local/sim-foundation/cli/xtask` | `cli` | `local/sim-foundation/crate/xtask` |
| `local/sim-kernel/cli/xtask` | `cli` | `local/sim-kernel/crate/xtask` |
| `local/sim-ledger/cli/xtask` | `cli` | `local/sim-ledger/crate/xtask` |
| `local/sim-music/cli/xtask` | `cli` | `local/sim-music/crate/xtask` |
| `local/sim-numbers/cli/xtask` | `cli` | `local/sim-numbers/crate/xtask` |
| `local/sim-office/cli/xtask` | `cli` | `local/sim-office/crate/xtask` |
| `local/sim-run/cli/xtask` | `cli` | `local/sim-run/crate/xtask` |
| `local/sim-runtime/cli/xtask` | `cli` | `local/sim-runtime/crate/xtask` |
| `local/sim-sdk/cli/xtask` | `cli` | `local/sim-sdk/crate/xtask` |
| `local/sim-sdk/site-device/glasses-hud` | `site-device` | `crate/sim-nest` |
| `local/sim-sdk/site-device/glasses-luma-ultra` | `site-device` | `crate/sim-nest` |
| `local/sim-shape/cli/xtask` | `cli` | `local/sim-shape/crate/xtask` |
| `local/sim-storage/cli/xtask` | `cli` | `local/sim-storage/crate/xtask` |
| `local/sim-stream/cli/xtask` | `cli` | `local/sim-stream/crate/xtask` |
| `local/sim-tooling/cli/xtask` | `cli` | `local/sim-tooling/crate/xtask` |
| `local/sim-tooling/site-device/desktop` | `site-device` | `local/sim-tooling/crate/xtask` |
| `local/sim-tooling/site-device/glasses` | `site-device` | `local/sim-tooling/crate/xtask` |
| `local/sim-tooling/site-device/glasses-3dof` | `site-device` | `local/sim-tooling/crate/xtask` |
| `local/sim-tooling/site-device/glasses-hud` | `site-device` | `local/sim-tooling/crate/xtask` |
| `local/sim-tooling/site-device/glasses-hud-camera` | `site-device` | `local/sim-tooling/crate/xtask` |
| `local/sim-tooling/site-device/glasses-luma-ultra` | `site-device` | `local/sim-tooling/crate/xtask` |
| `local/sim-tooling/site-device/glasses-stereo` | `site-device` | `local/sim-tooling/crate/xtask` |
| `local/sim-tooling/site-device/phone` | `site-device` | `local/sim-tooling/crate/xtask` |
| `local/sim-tooling/site-device/watch` | `site-device` | `local/sim-tooling/crate/xtask` |
| `local/sim-tooling/site-device/watch-glance-large` | `site-device` | `local/sim-tooling/crate/xtask` |
| `local/sim-tooling/site-device/watch-sleep` | `site-device` | `local/sim-tooling/crate/xtask` |
| `local/sim-tooling/site-device/watch-sport` | `site-device` | `local/sim-tooling/crate/xtask` |
| `local/sim-web/cli/xtask` | `cli` | `local/sim-web/crate/xtask` |
| `local/sim-web/site-device/desktop` | `site-device` | `local/sim-web/crate/sim-lib-view` |
| `local/sim-web/site-device/glasses` | `site-device` | `local/sim-web/crate/sim-lib-view` |
| `local/sim-web/site-device/glasses-3dof` | `site-device` | `local/sim-web/crate/sim-lib-view` |
| `local/sim-web/site-device/glasses-hud` | `site-device` | `local/sim-web/crate/sim-lib-view` |
| `local/sim-web/site-device/glasses-hud-camera` | `site-device` | `local/sim-web/crate/sim-lib-view` |
| `local/sim-web/site-device/glasses-luma-ultra` | `site-device` | `local/sim-web/crate/sim-lib-view` |
| `local/sim-web/site-device/glasses-stereo` | `site-device` | `local/sim-web/crate/sim-lib-view` |
| `local/sim-web/site-device/phone` | `site-device` | `local/sim-web/crate/sim-lib-view` |
| `local/sim-web/site-device/watch` | `site-device` | `local/sim-web/crate/sim-lib-view` |
| `local/sim-web/site-device/watch-glance-large` | `site-device` | `local/sim-web/crate/sim-lib-view` |
| `local/sim-web/site-device/watch-sleep` | `site-device` | `local/sim-web/crate/sim-lib-view` |
| `local/sim-web/site-device/watch-sport` | `site-device` | `local/sim-web/crate/sim-lib-view` |
| `model/sim-lib-agent` | `model-exchange` | `crate/sim-lib-agent` |
| `model/sim-lib-agent-runner-core` | `model-exchange` | `local/sim-agent-net/crate/sim-lib-agent-runner-core` |
| `model/sim-lib-agent-runner-core-recipe-output-contract-repair` | `model-exchange` | `crate/sim-lib-agent-runner-core-recipe-output-contract-repair` |
| `model/sim-lib-agent-runner-http` | `model-exchange` | `crate/sim-lib-agent-runner-http` |
| `model/sim-lib-agent-runner-local` | `model-exchange` | `crate/sim-lib-agent-runner-local` |
| `model/sim-lib-agent-runner-process` | `model-exchange` | `crate/sim-lib-agent-runner-process` |
| `model/sim-lib-openai-server` | `model-exchange` | `local/sim-agent-net/crate/sim-lib-openai-server` |
| `model/sim-lib-view-agent` | `model-exchange` | `crate/sim-lib-view-agent` |
| `site/sim-kernel` | `site` | `crate/sim-kernel` |
| `site/sim-lib-agent-runner-local` | `site` | `crate/sim-lib-agent-runner-local` |
| `site/sim-lib-numbers-f64` | `site` | `crate/sim-lib-numbers-f64` |
| `site/sim-lib-stream-cpal` | `site` | `crate/sim-lib-stream-cpal` |
| `site/sim-lib-topology` | `site` | `local/sim-stream/crate/sim-lib-topology` |
| `site/sim-macros` | `site` | `crate/sim-macros` |
| `site/sim-nest` | `site` | `crate/sim-nest` |
| `site/sim-run-core` | `site` | `crate/sim-run-core` |
| `site/sim-run-loaders` | `site` | `crate/sim-run-loaders` |
| `site/sim-wasm-abi` | `site` | `crate/sim-wasm-abi` |
| `site/xtask` | `site` | `local/sim-tooling/crate/xtask` |
| `syntax/algol` | `syntax` | `language/algol` |
| `syntax/binary` | `syntax` | `language/binary` |
| `syntax/binary-base64` | `syntax` | `language/binary-base64` |
| `syntax/bitwise` | `syntax` | `language/bitwise` |
| `syntax/bitwise-base64` | `syntax` | `language/bitwise-base64` |
| `syntax/bridge` | `syntax` | `language/bridge` |
| `syntax/chat` | `syntax` | `language/chat` |
| `syntax/compare` | `syntax` | `language/compare` |
| `syntax/config` | `syntax` | `language/config` |
| `syntax/doc` | `syntax` | `language/doc` |
| `syntax/index` | `syntax` | `language/index` |
| `syntax/json` | `syntax` | `language/json` |
| `syntax/lisp` | `syntax` | `language/lisp` |
| `syntax/lua` | `syntax` | `language/lua` |
| `syntax/mcp` | `syntax` | `language/mcp` |
| `syntax/mspdi` | `syntax` | `language/mspdi` |
| `syntax/odf` | `syntax` | `language/odf` |
| `syntax/ooxml` | `syntax` | `language/ooxml` |
| `syntax/pratt` | `syntax` | `language/pratt` |
| `view-edit/sim-lib-view` | `view-edit` | `local/sim-web/crate/sim-lib-view` |
| `view-edit/sim-lib-view-bridge` | `view-edit` | `crate/sim-lib-view-bridge` |
| `view-edit/sim-lib-view-device` | `view-edit` | `crate/sim-lib-view-device` |
| `view-edit/sim-lib-view-spatial` | `view-edit` | `crate/sim-lib-view-spatial` |
| `view-edit/sim-lib-view-wasm-frame` | `view-edit` | `crate/sim-lib-view-wasm-frame` |
| `view-edit/sim-lib-web-bridge` | `view-edit` | `crate/sim-lib-web-bridge` |
| `view-edit/sim-nest` | `view-edit` | `crate/sim-nest` |
| `view-edit/sim-web-shell` | `view-edit` | `crate/sim-web-shell` |
| `view-edit/xtask` | `view-edit` | `local/sim-tooling/crate/xtask` |
| `view/sim-lib-doc-core` | `view` | `crate/sim-lib-doc-core` |
| `view/sim-lib-doc-markup` | `view` | `crate/sim-lib-doc-markup` |
| `view/sim-lib-doc-surface` | `view` | `crate/sim-lib-doc-surface` |
| `view/sim-lib-view` | `view` | `local/sim-web/crate/sim-lib-view` |
| `view/sim-lib-view-agent` | `view` | `crate/sim-lib-view-agent` |
| `view/sim-lib-view-bridge` | `view` | `crate/sim-lib-view-bridge` |
| `view/sim-lib-view-codec` | `view` | `crate/sim-lib-view-codec` |
| `view/sim-lib-view-daw` | `view` | `crate/sim-lib-view-daw` |
| `view/sim-lib-view-device` | `view` | `crate/sim-lib-view-device` |
| `view/sim-lib-view-doc` | `view` | `local/sim-web/crate/sim-lib-view-doc` |
| `view/sim-lib-view-math` | `view` | `crate/sim-lib-view-math` |
| `view/sim-lib-view-spatial` | `view` | `crate/sim-lib-view-spatial` |
| `view/sim-lib-view-wasm-frame` | `view` | `crate/sim-lib-view-wasm-frame` |
| `view/sim-lib-view-wrist` | `view` | `crate/sim-lib-view-wrist` |
| `view/sim-lib-web-bridge` | `view` | `crate/sim-lib-web-bridge` |
| `view/sim-nest` | `view` | `crate/sim-nest` |
| `view/sim-view-tty` | `view` | `crate/sim-view-tty` |
| `view/xtask` | `view` | `local/sim-tooling/crate/xtask` |
| `wire/binary` | `wire` | `language/binary` |
| `wire/binary-base64` | `wire` | `language/binary-base64` |
| `wire/bitwise` | `wire` | `language/bitwise` |
| `wire/bitwise-base64` | `wire` | `language/bitwise-base64` |
| `wire/bridge` | `wire` | `language/bridge` |
| `wire/chat` | `wire` | `language/chat` |
| `wire/config` | `wire` | `language/config` |
| `wire/doc` | `wire` | `language/doc` |
| `wire/index` | `wire` | `language/index` |
| `wire/mcp` | `wire` | `language/mcp` |
