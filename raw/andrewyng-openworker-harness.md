# OpenWorker Harness SDK (andrewyng/openworker, harness/README.md)

Source URL: https://github.com/andrewyng/openworker/blob/main/harness/README.md
Repository: https://github.com/andrewyng/openworker
Docs: https://openworker.com/docs/sdk/
License: MIT
Captured: 2026-11-16

## Main Points

- Tagline: "Build your app. OpenWorker handles the agents." The SDK lets developers embed agents in their own applications. The agents use tools, delegate work, and collaborate. Examples given: a coding agent that implements and verifies changes, a support agent that investigates and acts, and teams of agents coordinating across systems.
- Under active development: try it and file issues, but SDK pull requests are on hold while the API evolves.
- **Division of responsibility.** The application owns the UI, auth, user and session ownership, model choice, tool choice, and policies. OpenWorker owns the agent loop, model calls, approvals, and durable sessions.
- **Architecture.** One Rust engine powers both SDKs. The TypeScript SDK runs it as a child process; the Rust SDK can embed it in-process. Browser code talks to the app's server or desktop IPC, never to the harness directly. **OpenShell** isolates configured shell and file execution while the agent loop stays in the trusted harness. App callbacks run with the app's own privileges. The existing OpenWorker Desktop App uses a separate Python engine.
- **Getting started.** The recommended path is a builder skill for coding agents: `npx @openworkerai/openworker-harness-builder --agent claude --project .` (or `--agent codex`, `--global`). It ships SDK instructions and runnable examples; the tested SDK pin is in `references/installation.json`.
- **Manual TypeScript quickstart.** `npm install @openworkerai/harness-sdk` → `Harness.start({ stateDir, sandbox: 'off' })` → `harness.setModelProvider(...)` → `harness.createAgent({ name, instructions, defaultModel, tools, planning, memory, scheduling })` → `agent.newSession()` → `session.run(...)` → `result.finalOutput`. Reuse the session for follow-ups; call `harness.shutdown()` in `finally`.
- **Providers.** The example uses the OpenAI Responses API. `OPENWORKER_MODEL_URL` can point at any Responses-compatible endpoint, and cloud and local providers are supported. Credentials are application-owned (`OPENAI_API_KEY`, `storage: 'memory'`).
- Agent identity is immutable: changing instructions, tools, or approvals requires a new agent name.
- **SDK features:**
  - Model/tool loop with streaming, cancellation, and context compaction.
  - Durable sessions that survive restarts, with explicit recovery that avoids blindly replaying uncertain actions.
  - Approvals, session grants, and optional LLM-assisted review.
  - Guardrails, hooks, and OpenShell isolation.
  - Sub-agents and teams with durable messages and boards.
  - Opt-in observability: traces, token usage, and export to Langfuse and similar tools.
- **Deployment.** Runs inside a desktop app, a Node process, or a container. A separate agent service is optional (API/worker split, shared PostgreSQL); local apps can use SQLite. AWS, Azure, GCP, and private Kubernetes guides are "experimental reference" paths.
- **Example apps:**
  - File organizer: custom tools, directory restrictions, per-operation approvals.
  - Code Atlas: an Electron app that explains a code directory.
  - PDF Notes: a web app for questions about an attached PDF.
  - Arcade Studio: builds games and keeps a library of approved versions.
- **Safety guidance:**
  - Callbacks keep app privileges, and a workspace path alone does not confine filesystem access.
  - Keep credentials and durable state out of model-readable files.
  - Approval requests need real user decisions; stopping observation does not cancel execution.
  - Reconcile unknown tool outcomes before retrying.
  - Use public SDK interfaces rather than internal tables.
- **Caveats:**
  - The API is evolving.
  - Rust apps use a pinned source checkout; npm publication does not imply a Cargo release.
  - npm optional dependencies must stay enabled for the native runtime.
  - Cloud paths need qualification before production use.
  - There is no evaluation or benchmark section.

## Notable Links

- Docs: https://openworker.com/docs/sdk/
- Issues: https://github.com/andrewyng/openworker/issues
- In-repo guides under `docs/harness/guides/`: providers, sessions, tools, guardrails, openshell, observability, deployment, alignment, compliance
