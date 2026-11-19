# openai/codex (Codex CLI)

Source URL: https://github.com/openai/codex
Also viewed: https://github.com/openai/codex/blob/main/sdk/typescript/README.md
Docs: https://developers.openai.com/codex
License: Apache-2.0
Captured: 2026-11-17

## Main Points (repository README)

- OpenAI's coding agent that runs locally. The repository's About text calls it a "Lightweight coding agent that runs in your terminal." Start it with `codex`.
- **Surfaces:**
  - The CLI.
  - An IDE extension for VS Code, Cursor, and Windsurf (https://developers.openai.com/codex/ide).
  - A desktop app (`codex app`).
  - A cloud agent, Codex Web, at https://chatgpt.com/codex.
- **Install:**
  - macOS/Linux: `curl -fsSL https://chatgpt.com/codex/install.sh | sh`
  - Windows: `powershell -ExecutionPolicy ByPass -c "irm https://chatgpt.com/codex/install.ps1 | iex"`
  - `npm install -g @openai/codex`
  - `brew install --cask codex`
  - Release binaries for macOS (arm64/x86_64) and Linux musl (x86_64/arm64).
  - The installers download from releases.openai.com and fall back to GitHub Releases; set `CODEX_INSTALLER_USE_RELEASES_OPENAI_COM=false` to force GitHub.
- **Auth:** "Sign in with ChatGPT" is recommended and works with Plus, Pro, Business, Edu, and Enterprise plans. API-key sign-in is supported with extra setup (https://developers.openai.com/codex/auth#sign-in-with-an-api-key).
- The README does not document sandboxing, approvals, config files, MCP, exec mode, or providers; it defers to the docs site.
- Top-level folders include `codex-rs`, `codex-cli`, and `sdk` (subfolders `typescript`, `python`, `python-runtime`). The README does not state the implementation language.
- The repo page showed about 135.6k stars, 21.5k forks, and 13,725 commits on the capture date.

## TypeScript SDK (sdk/typescript/README.md)

- Package `@openai/codex-sdk` (Node 18+). It **wraps the `codex` CLI**: it "spawns the CLI and exchanges JSONL events over stdin/stdout."
- Usage: `new Codex()` → `codex.startThread()` → `thread.run(...)` returns `turn.finalResponse` and `turn.items`. Calling `run()` again on the same thread continues the conversation.
- `runStreamed()` yields structured events such as `item.completed`, and `turn.completed` with usage.
- Structured output: pass a per-turn JSON Schema as `outputSchema` (Zod schemas can be converted with `zodToJsonSchema`).
- Images: `{ type: "local_image", path }` entries are passed to the CLI as `--image`.
- Threads persist in `~/.codex/sessions` and can be resumed with `codex.resumeThread(id)`.
- The working directory must be a Git repository by default; pass `workingDirectory` and optionally `skipGitRepoCheck: true`.
- Environment: the `env` option replaces the inherited environment; `baseUrl` maps to `--config openai_base_url=...`.
- Config: `config` objects are flattened into `--config key=value` TOML overrides, and `configOverrides` passes raw TOML. Sandbox and permission settings appear only through config examples, such as `sandbox_workspace_write: { network_access: true }` and `default_permissions: "audit"`.

## Notable Links

- Docs: https://developers.openai.com/codex
- Install/build: https://github.com/openai/codex/blob/main/docs/install.md
- Contributing: https://github.com/openai/codex/blob/main/docs/contributing.md
- Open source fund: https://github.com/openai/codex/blob/main/docs/open-source-fund.md
- Security: https://github.com/openai/codex/blob/main/SECURITY.md
- Changelog: https://github.com/openai/codex/blob/main/CHANGELOG.md
