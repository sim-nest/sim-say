# SIM Index Features

Generated from `docs/index/index.cards.jsonl`.

| Feature | Subject | Index page | Specimens | Summary |
| --- | --- | --- | ---: | --- |
| `feature/sim-agent-net/agent-server-tools` | `crate/sim-lib-server` | [features/feature--sim-agent-net--agent-server-tools.md](../index/features/feature--sim-agent-net--agent-server-tools.md) | 0 | Expose agent-facing server, skill, and OpenAI gateway libraries for model-connected hosts. |
| `feature/sim-agent-net/bridge-model-exchange` | `crate/sim-lib-agent` | [features/feature--sim-agent-net--bridge-model-exchange.md](../index/features/feature--sim-agent-net--bridge-model-exchange.md) | 0 | Shape model exchanges as Bridge packets with agent and bridge runtime support. |
| `feature/sim-agent-net/eval-fabric-sites` | `crate/sim-lib-agent-runner-local` | [features/feature--sim-agent-net--eval-fabric-sites.md](../index/features/feature--sim-agent-net--eval-fabric-sites.md) | 0 | Place model and stream work through loadable runner, local model, and content-addressed fleet libraries. |
| `feature/sim-agent-net/forge-intent` | `crate/sim-lib-forge` | [features/feature--sim-agent-net--forge-intent.md](../index/features/feature--sim-agent-net--forge-intent.md) | 0 | Compile high-level intent records into checked Forge output through the loadable Forge runtime library. |
| `feature/sim-agent-net/mcp-server` | `crate/sim-lib-mcp` | [features/feature--sim-agent-net--mcp-server.md](../index/features/feature--sim-agent-net--mcp-server.md) | 0 | Serve MCP requests through the loaded sim-lib-mcp command and runtime libraries. |
| `feature/sim-citizen/citizen-read-constructs` | `crate/sim-citizen` | [features/feature--sim-citizen--citizen-read-constructs.md](../index/features/feature--sim-citizen--citizen-read-constructs.md) | 1 | Expose Rust values as runtime citizens with class members, registry rows, and read-construct round trips. |
| `feature/sim-codecs/bridge-packet-codec` | `crate/sim-codec-bridge` | [features/feature--sim-codecs--bridge-packet-codec.md](../index/features/feature--sim-codecs--bridge-packet-codec.md) | 0 | Encode and decode Bridge packet workflow data through the Bridge wire grammar. |
| `feature/sim-codecs/codec` | `crate/sim-codec` | [features/feature--sim-codecs--codec.md](../index/features/feature--sim-codecs--codec.md) | 1 | Define codec positions, limits, syntax surfaces, wire surfaces, and loadable codec runtime libraries. |
| `feature/sim-codecs/pratt` | `crate/sim-codec-pratt` | [features/feature--sim-codecs--pratt.md](../index/features/feature--sim-codecs--pratt.md) | 0 | Parse operator-oriented expression languages through the Pratt codec surface. |
| `feature/sim-foundation/cookbook` | `crate/sim-cookbook` | [features/feature--sim-foundation--cookbook.md](../index/features/feature--sim-foundation--cookbook.md) | 0 | Describe reusable recipe metadata and generated cookbook records consumed by public docs and tooling. |
| `feature/sim-foundation/host-primitives` | `crate/sim-lib-net-core` | [features/feature--sim-foundation--host-primitives.md](../index/features/feature--sim-foundation--host-primitives.md) | 0 | Provide shared network and surface-card helper crates for host-facing runtime libraries. |
| `feature/sim-foundation/table-dir-core` | `crate/sim-table-core` | [features/feature--sim-foundation--table-dir-core.md](../index/features/feature--sim-foundation--table-dir-core.md) | 0 | Define shared table and directory contracts used by storage, index, and host-facing libraries. |
| `feature/sim-foundation/value-helpers` | `crate/sim-value` | [features/feature--sim-foundation--value-helpers.md](../index/features/feature--sim-foundation--value-helpers.md) | 0 | Provide shared value conversion and table-field helpers for reusable runtime libraries. |
| `feature/sim-numbers/numbers` | `crate/sim-lib-numbers-core` | [features/feature--sim-numbers--numbers.md](../index/features/feature--sim-numbers--numbers.md) | 1 | Provide arithmetic, exact, floating, symbolic, tensor, and statistics number domains as loadable libraries. |
| `feature/sim-run/bootloader` | `crate/sim-run-core` | [features/feature--sim-run--bootloader.md](../index/features/feature--sim-run--bootloader.md) | 2 | Start product commands through the shared bootloader and loaded runtime libraries. |
| `feature/sim-run/glasses` | `crate/sim-run` | [features/feature--sim-run--glasses.md](../index/features/feature--sim-run--glasses.md) | 0 | Start modeled or hardware-backed glasses plans through the shared command bootloader. |
| `feature/sim-run/index` | `local/sim-run/crate/xtask` | [features/feature--sim-run--index.md](../index/features/feature--sim-run--index.md) | 1 | Expose generated package, card, surface, and recipe facts as a checked SIM Index fragment. |
| `feature/sim-run/index-table-dir` | `crate/sim-lib-index` | [features/feature--sim-run--index-table-dir.md](../index/features/feature--sim-run--index-table-dir.md) | 1 | Expose the embedded SIM Index as immutable Table/Dir collections for loaded runtime code. |
| `feature/sim-run/repl` | `crate/sim-lib-repl` | [features/feature--sim-run--repl.md](../index/features/feature--sim-run--repl.md) | 1 | Run a SIM read-eval-print loop through the loaded REPL library and command surface. |
| `feature/sim-run/runtime-index` | `crate/sim-lib-index` | [features/feature--sim-run--runtime-index.md](../index/features/feature--sim-run--runtime-index.md) | 4 | Explore the merged SIM Index through the bootloader as stable Table/Dir rows and structured query output. |
| `feature/sim-run/terminal-surface` | `crate/sim-view-tty` | [features/feature--sim-run--terminal-surface.md](../index/features/feature--sim-run--terminal-surface.md) | 1 | Render and interpret terminal view intents through the loaded TTY surface library. |
| `feature/sim-run/watch` | `crate/sim-run` | [features/feature--sim-run--watch.md](../index/features/feature--sim-run--watch.md) | 0 | Start modeled, imported, or live watch plans through the shared command bootloader. |
| `feature/sim-runtime/capabilities-read-eval` | `crate/sim-lib-core` | [features/feature--sim-runtime--capabilities-read-eval.md](../index/features/feature--sim-runtime--capabilities-read-eval.md) | 1 | Gate diminished read-eval and surface packing through explicit runtime libraries and capability checks. |
| `feature/sim-runtime/host-exec` | `crate/sim-lib-exec` | [features/feature--sim-runtime--host-exec.md](../index/features/feature--sim-runtime--host-exec.md) | 0 | Expose bounded process execution as a capability-gated host primitive outside the kernel. |
| `feature/sim-runtime/library-loading` | `crate/sim-lib-standard-core` | [features/feature--sim-runtime--library-loading.md](../index/features/feature--sim-runtime--library-loading.md) | 1 | Load standard and language-profile runtime libraries through stable export records. |
| `feature/sim-runtime/organs` | `crate/sim-lib-binding` | [features/feature--sim-runtime--organs.md](../index/features/feature--sim-runtime--organs.md) | 0 | Provide binding, control, logic, pattern, mutation, and sequence organs as loadable runtime libraries. |
| `feature/sim-shape/shape` | `crate/sim-shape` | [features/feature--sim-shape--shape.md](../index/features/feature--sim-shape--shape.md) | 1 | Define reusable Shape matching, binding, citizen projection, and grammar contracts for runtime values. |
| `feature/sim-storage/host-storage-primitives` | `crate/sim-table-fs` | [features/feature--sim-storage--host-storage-primitives.md](../index/features/feature--sim-storage--host-storage-primitives.md) | 0 | Connect file, database, and HTTP storage crates to the shared Table and Dir backend shape. |
| `feature/sim-storage/table-dir-backends` | `crate/sim-table-hash` | [features/feature--sim-storage--table-dir-backends.md](../index/features/feature--sim-storage--table-dir-backends.md) | 1 | Provide hash, lazy, override, and list-backed Table/Dir implementations for reusable storage libraries. |
| `feature/sim-stream/stream-protocol-helpers` | `crate/sim-lib-stream-core` | [features/feature--sim-stream--stream-protocol-helpers.md](../index/features/feature--sim-stream--stream-protocol-helpers.md) | 1 | Provide rank, topology, stream core, device, wrist, and XR helpers as loadable stream libraries. |
| `feature/sim-tooling/generated-docs` | `local/sim-tooling/crate/xtask` | [features/feature--sim-tooling--generated-docs.md](../index/features/feature--sim-tooling--generated-docs.md) | 0 | Generate repo contracts, feature maps, card indexes, and index fragments through xtask. |
| `feature/sim-web/device-surfaces` | `crate/sim-lib-view` | [features/feature--sim-web--device-surfaces.md](../index/features/feature--sim-web--device-surfaces.md) | 0 | Rank and project view surfaces against desktop, phone, watch, and glasses device profiles. |
| `feature/sim-web/view-surface` | `crate/sim-lib-view` | [features/feature--sim-web--view-surface.md](../index/features/feature--sim-web--view-surface.md) | 0 | Expose view and edit surfaces through sim-lib-view so codecs can render and reverse surface data. |
| `feature/sim-web/web-shell-host` | `crate/sim-web-shell` | [features/feature--sim-web--web-shell-host.md](../index/features/feature--sim-web--web-shell-host.md) | 0 | Serve browser-facing surfaces through loaded web shell runtime libraries and command entry points. |

## Surface Rows

| Surface | Kind | Subject |
| --- | --- | --- |
| `cli/atelier` | `cli` | `crate/sim-web-shell` |
| `cli/browse` | `cli` | `crate/sim-web-shell` |
| `cli/citizen-roundtrip` | `cli` | `crate/citizen-roundtrip` |
| `cli/glasses` | `cli` | `crate/sim-run` |
| `cli/index` | `cli` | `crate/sim-lib-index` |
| `cli/mcp` | `cli` | `crate/sim-lib-mcp` |
| `cli/repl` | `cli` | `crate/sim-lib-repl` |
| `cli/serve` | `cli` | `crate/sim-web-shell` |
| `cli/sim-codec-compare` | `cli` | `crate/sim-codec-compare` |
| `cli/sim-fabric-cadr-fixture` | `cli` | `crate/sim-lib-stream-fabric` |
| `cli/sim-lib-agent-runner-core-recipe-output-contract-repair` | `cli` | `crate/sim-lib-agent-runner-core-recipe-output-contract-repair` |
| `cli/sim-lib-stream-fabric` | `cli` | `crate/sim-lib-stream-fabric` |
| `cli/sim-mcp-server` | `cli` | `crate/sim-mcp-server` |
| `cli/sim-run` | `cli` | `crate/sim-run` |
| `cli/sim-shape-recipe-exact-bool-shape` | `cli` | `crate/sim-shape-recipe-exact-bool-shape` |
| `cli/sim-shape-recipe-shape-grammar-contract` | `cli` | `crate/sim-shape-recipe-shape-grammar-contract` |
| `cli/sim-web-shell` | `cli` | `crate/sim-web-shell` |
| `cli/watch` | `cli` | `crate/sim-run` |
| `docs/sim-agent-net/generated` | `docs` | `doc-set/sim-agent-net/generated` |
| `docs/sim-citizen/generated` | `docs` | `doc-set/sim-citizen/generated` |
| `docs/sim-codecs/generated` | `docs` | `doc-set/sim-codecs/generated` |
| `docs/sim-foundation/generated` | `docs` | `doc-set/sim-foundation/generated` |
| `docs/sim-numbers/generated` | `docs` | `doc-set/sim-numbers/generated` |
| `docs/sim-run/generated` | `docs` | `doc-set/sim-run/generated` |
| `docs/sim-runtime/generated` | `docs` | `doc-set/sim-runtime/generated` |
| `docs/sim-shape/generated` | `docs` | `doc-set/sim-shape/generated` |
| `docs/sim-storage/generated` | `docs` | `doc-set/sim-storage/generated` |
| `docs/sim-stream/generated` | `docs` | `doc-set/sim-stream/generated` |
| `docs/sim-tooling/generated` | `docs` | `doc-set/sim-tooling/generated` |
| `docs/sim-web/generated` | `docs` | `doc-set/sim-web/generated` |
| `local/sim-agent-net/cli/xtask` | `cli` | `local/sim-agent-net/crate/xtask` |
| `local/sim-citizen/cli/xtask` | `cli` | `local/sim-citizen/crate/xtask` |
| `local/sim-codecs/cli/xtask` | `cli` | `local/sim-codecs/crate/xtask` |
| `local/sim-foundation/cli/xtask` | `cli` | `local/sim-foundation/crate/xtask` |
| `local/sim-numbers/cli/xtask` | `cli` | `local/sim-numbers/crate/xtask` |
| `local/sim-run/cli/xtask` | `cli` | `local/sim-run/crate/xtask` |
| `local/sim-runtime/cli/xtask` | `cli` | `local/sim-runtime/crate/xtask` |
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
| `local/sim-web/site-device/desktop` | `site-device` | `crate/sim-lib-view` |
| `local/sim-web/site-device/glasses` | `site-device` | `crate/sim-lib-view` |
| `local/sim-web/site-device/glasses-3dof` | `site-device` | `crate/sim-lib-view` |
| `local/sim-web/site-device/glasses-hud` | `site-device` | `crate/sim-lib-view` |
| `local/sim-web/site-device/glasses-hud-camera` | `site-device` | `crate/sim-lib-view` |
| `local/sim-web/site-device/glasses-luma-ultra` | `site-device` | `crate/sim-lib-view` |
| `local/sim-web/site-device/glasses-stereo` | `site-device` | `crate/sim-lib-view` |
| `local/sim-web/site-device/phone` | `site-device` | `crate/sim-lib-view` |
| `local/sim-web/site-device/watch` | `site-device` | `crate/sim-lib-view` |
| `local/sim-web/site-device/watch-glance-large` | `site-device` | `crate/sim-lib-view` |
| `local/sim-web/site-device/watch-sleep` | `site-device` | `crate/sim-lib-view` |
| `local/sim-web/site-device/watch-sport` | `site-device` | `crate/sim-lib-view` |
| `model/sim-lib-agent` | `model-exchange` | `crate/sim-lib-agent` |
| `model/sim-lib-agent-runner-core` | `model-exchange` | `crate/sim-lib-agent-runner-core` |
| `model/sim-lib-agent-runner-core-recipe-output-contract-repair` | `model-exchange` | `crate/sim-lib-agent-runner-core-recipe-output-contract-repair` |
| `model/sim-lib-agent-runner-http` | `model-exchange` | `crate/sim-lib-agent-runner-http` |
| `model/sim-lib-agent-runner-local` | `model-exchange` | `crate/sim-lib-agent-runner-local` |
| `model/sim-lib-agent-runner-process` | `model-exchange` | `crate/sim-lib-agent-runner-process` |
| `model/sim-lib-openai-server` | `model-exchange` | `crate/sim-lib-openai-server` |
| `model/sim-lib-view-agent` | `model-exchange` | `crate/sim-lib-view-agent` |
| `site/sim-lib-agent-runner-local` | `site` | `crate/sim-lib-agent-runner-local` |
| `site/sim-lib-numbers-f64` | `site` | `crate/sim-lib-numbers-f64` |
| `site/sim-lib-topology` | `site` | `crate/sim-lib-topology` |
| `site/sim-macros` | `site` | `crate/sim-macros` |
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
| `syntax/pratt` | `syntax` | `language/pratt` |
| `view-edit/sim-lib-view` | `view-edit` | `crate/sim-lib-view` |
| `view-edit/sim-lib-view-bridge` | `view-edit` | `crate/sim-lib-view-bridge` |
| `view-edit/sim-lib-view-device` | `view-edit` | `crate/sim-lib-view-device` |
| `view-edit/sim-lib-view-spatial` | `view-edit` | `crate/sim-lib-view-spatial` |
| `view-edit/sim-lib-view-wasm-frame` | `view-edit` | `crate/sim-lib-view-wasm-frame` |
| `view-edit/sim-lib-web-bridge` | `view-edit` | `crate/sim-lib-web-bridge` |
| `view-edit/sim-web-shell` | `view-edit` | `crate/sim-web-shell` |
| `view-edit/xtask` | `view-edit` | `local/sim-tooling/crate/xtask` |
| `view/sim-lib-view` | `view` | `crate/sim-lib-view` |
| `view/sim-lib-view-agent` | `view` | `crate/sim-lib-view-agent` |
| `view/sim-lib-view-bridge` | `view` | `crate/sim-lib-view-bridge` |
| `view/sim-lib-view-codec` | `view` | `crate/sim-lib-view-codec` |
| `view/sim-lib-view-daw` | `view` | `crate/sim-lib-view-daw` |
| `view/sim-lib-view-device` | `view` | `crate/sim-lib-view-device` |
| `view/sim-lib-view-doc` | `view` | `crate/sim-lib-view-doc` |
| `view/sim-lib-view-math` | `view` | `crate/sim-lib-view-math` |
| `view/sim-lib-view-spatial` | `view` | `crate/sim-lib-view-spatial` |
| `view/sim-lib-view-wasm-frame` | `view` | `crate/sim-lib-view-wasm-frame` |
| `view/sim-lib-view-wrist` | `view` | `crate/sim-lib-view-wrist` |
| `view/sim-lib-web-bridge` | `view` | `crate/sim-lib-web-bridge` |
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
