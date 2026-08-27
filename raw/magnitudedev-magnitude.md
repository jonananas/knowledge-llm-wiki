# magnitudedev/magnitude

Source URL: https://github.com/magnitudedev/magnitude
Fetch date: 2026-08-27

Related docs:
- https://docs.magnitude.dev/
- https://docs.magnitude.dev/get-started
- https://docs.magnitude.dev/models
- https://docs.magnitude.dev/inference-engine
- https://docs.magnitude.dev/custom-endpoints
- https://docs.magnitude.dev/skills
- https://docs.magnitude.dev/reference
- https://docs.magnitude.dev/troubleshooting

## Summary

`magnitudedev/magnitude` is the GitHub repository for Magnitude, an open-source local agent with local model inference built in. It is positioned as a way to run agent workflows privately and offline after setup, without separately configuring Ollama, LM Studio, llama.cpp, or another model server.

Magnitude profiles the user's hardware, recommends compatible local model configurations, downloads models, configures inference settings, and runs those models inside the agent. The repo and docs emphasize agent workloads rather than generic chat alone.

## Main points

- Magnitude installs through the `@magnitudedev/cli` npm package.
- Basic usage is `npm install -g @magnitudedev/cli`, then `magnitude` from the project directory.
- Supported platforms are macOS and Linux. Windows support requires WSL; native Windows is not currently supported.
- On first launch, Magnitude profiles local hardware and ranks compatible model configurations.
- The ranking considers model intelligence, estimated speed, quantization quality, memory fit, and context size.
- Magnitude manages model files under `~/.magnitude/models` and derived caches under `~/.magnitude/cache`.
- It can scan Hugging Face Hub cache locations for compatible GGUF models.
- The local inference runtime is written in Rust on top of llama.cpp and packaged with Magnitude.
- Magnitude starts, loads, unloads, and stops local models as part of the agent runtime.
- It monitors memory while local models load or run, and can stop a model before low memory destabilizes the machine.
- It normalizes differences across local models, including reasoning formats, tool-call formats, chat templates, and conversation-history conventions.
- It supports custom OpenAI-compatible Chat Completions endpoints through `~/.magnitude/config.json`.
- Privacy and offline claims apply to built-in local models. With a custom endpoint, requests go to the configured endpoint.
- Web search is available through Exa if `EXA_API_KEY` is set.
- Skills can extend Magnitude with browser, spreadsheet, presentation, document, and PDF capabilities. The docs recommend reviewing skill source before installing because skills may run commands, install dependencies, open websites, or interact with external services.
- The repository is Apache-2.0 licensed.

## Differentiation

Magnitude's stated difference from Ollama, LM Studio, and Hermes is integration. Ollama and LM Studio run local models, and Hermes is an agent that can use local models. Magnitude combines agent and local inference setup: it profiles hardware, recommends and downloads models, configures runtime behavior, then runs the selected model inside the agent.

The strongest technical positioning is not merely "local model runner"; it is hardware-aware model selection and runtime lifecycle management for agents.

## Operational notes

- More memory allows larger models, but there is no fixed minimum hardware requirement in the docs.
- Catalog speed is an estimate. Actual tokens per second depend on prompt length, other running applications, and exact model revision.
- Downloaded, loaded, running, and unloaded are distinct states.
- Long conversations incur prefill work before generation, though compatible prompt state can be reused.
- The troubleshooting docs caution against deleting `~/.magnitude` as a general fix because it contains models, sessions, settings, and caches.
- Session logs may include paths, prompts, and project information and should be reviewed before sharing.

## Links

- Repository: https://github.com/magnitudedev/magnitude
- Documentation index: https://docs.magnitude.dev/llms.txt
- Get Started: https://docs.magnitude.dev/get-started
- Models: https://docs.magnitude.dev/models
- Local Inference: https://docs.magnitude.dev/inference-engine
- Custom endpoints: https://docs.magnitude.dev/custom-endpoints
- Skills: https://docs.magnitude.dev/skills
- Reference: https://docs.magnitude.dev/reference
