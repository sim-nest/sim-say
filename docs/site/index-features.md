# SIM Index Features

Generated from `docs/index/index.cards.jsonl`.

| Feature | Subject | Index page | Specimens | Summary |
| --- | --- | --- | ---: | --- |
| `feature/sim-agent-net/mcp-server` | `crate/sim-lib-mcp` | [features/feature--sim-agent-net--mcp-server.md](../index/features/feature--sim-agent-net--mcp-server.md) | 0 | Serve MCP requests through the loaded sim-lib-mcp command and runtime libraries. |
| `feature/sim-agent-net/model-packet-workflow` | `crate/sim-lib-agent` | [features/feature--sim-agent-net--model-packet-workflow.md](../index/features/feature--sim-agent-net--model-packet-workflow.md) | 0 | Shape model exchanges as Bridge packets with agent and bridge runtime support. |
| `feature/sim-codecs/bridge-packet-codec` | `crate/sim-codec-bridge` | [features/feature--sim-codecs--bridge-packet-codec.md](../index/features/feature--sim-codecs--bridge-packet-codec.md) | 0 | Encode and decode Bridge packet workflow data through the Bridge wire grammar. |
| `feature/sim-codecs/codec-core` | `crate/sim-codec` | [features/feature--sim-codecs--codec-core.md](../index/features/feature--sim-codecs--codec-core.md) | 0 | Define codec positions, limits, and the domain codec runtime library used by concrete codecs. |
| `feature/sim-codecs/pratt-operator-language` | `crate/sim-codec-pratt` | [features/feature--sim-codecs--pratt-operator-language.md](../index/features/feature--sim-codecs--pratt-operator-language.md) | 0 | Parse operator-oriented expression languages through the Pratt codec surface. |
| `feature/sim-run/bootloader` | `crate/sim-run-core` | [features/feature--sim-run--bootloader.md](../index/features/feature--sim-run--bootloader.md) | 2 | Start product commands through the shared bootloader and loaded runtime libraries. |
| `feature/sim-run/glasses` | `crate/sim-run` | [features/feature--sim-run--glasses.md](../index/features/feature--sim-run--glasses.md) | 0 | Start modeled or hardware-backed glasses plans through the shared command bootloader. |
| `feature/sim-run/index` | `local/sim-run/crate/xtask` | [features/feature--sim-run--index.md](../index/features/feature--sim-run--index.md) | 1 | Expose generated package, card, surface, and recipe facts as a checked SIM Index fragment. |
| `feature/sim-run/index-table-dir` | `crate/sim-lib-index` | [features/feature--sim-run--index-table-dir.md](../index/features/feature--sim-run--index-table-dir.md) | 1 | Expose the embedded SIM Index as immutable Table/Dir collections for loaded runtime code. |
| `feature/sim-run/repl` | `crate/sim-lib-repl` | [features/feature--sim-run--repl.md](../index/features/feature--sim-run--repl.md) | 1 | Run a SIM read-eval-print loop through the loaded REPL library and command surface. |
| `feature/sim-run/runtime-index` | `crate/sim-lib-index` | [features/feature--sim-run--runtime-index.md](../index/features/feature--sim-run--runtime-index.md) | 4 | Explore the merged SIM Index through the bootloader as stable Table/Dir rows and structured query output. |
| `feature/sim-run/terminal-surface` | `crate/sim-view-tty` | [features/feature--sim-run--terminal-surface.md](../index/features/feature--sim-run--terminal-surface.md) | 1 | Render and interpret terminal view intents through the loaded TTY surface library. |
| `feature/sim-run/watch` | `crate/sim-run` | [features/feature--sim-run--watch.md](../index/features/feature--sim-run--watch.md) | 0 | Start modeled, imported, or live watch plans through the shared command bootloader. |
| `feature/sim-tooling/generated-docs` | `local/sim-tooling/crate/xtask` | [features/feature--sim-tooling--generated-docs.md](../index/features/feature--sim-tooling--generated-docs.md) | 0 | Generate repo contracts, feature maps, card indexes, and index fragments through xtask. |
| `feature/sim-web/view-surface` | `crate/sim-lib-view` | [features/feature--sim-web--view-surface.md](../index/features/feature--sim-web--view-surface.md) | 0 | Expose view and edit surfaces through sim-lib-view so codecs can render and reverse surface data. |

## Surface Rows

| Surface | Kind | Subject |
| --- | --- | --- |
| `cli/atelier` | `cli` | `crate/sim-web-shell` |
| `cli/browse` | `cli` | `crate/sim-web-shell` |
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
| `docs/sim-codecs/generated` | `docs` | `doc-set/sim-codecs/generated` |
| `docs/sim-foundation/generated` | `docs` | `doc-set/sim-foundation/generated` |
| `docs/sim-run/generated` | `docs` | `doc-set/sim-run/generated` |
| `docs/sim-shape/generated` | `docs` | `doc-set/sim-shape/generated` |
| `docs/sim-tooling/generated` | `docs` | `doc-set/sim-tooling/generated` |
| `docs/sim-web/generated` | `docs` | `doc-set/sim-web/generated` |
| `local/sim-agent-net/cli/xtask` | `cli` | `local/sim-agent-net/crate/xtask` |
| `local/sim-codecs/cli/xtask` | `cli` | `local/sim-codecs/crate/xtask` |
| `local/sim-foundation/cli/xtask` | `cli` | `local/sim-foundation/crate/xtask` |
| `local/sim-run/cli/xtask` | `cli` | `local/sim-run/crate/xtask` |
| `local/sim-shape/cli/xtask` | `cli` | `local/sim-shape/crate/xtask` |
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
