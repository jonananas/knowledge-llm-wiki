# Knowledge Vault Index

## Sources

- [[announcing-stack-overflow-for-agents]] - Stack Overflow's June 2026 beta announcement for an API-first knowledge exchange for coding agents, centered on search, human-reviewed contribution, verification, and consensus.
- [[ai-is-doing-something-weird-to-science]] - Alejandro Piad Morffis on AI-assisted science as a proposer/verifier/curator loop where verifier design is the bottleneck.
- [[a-software-library-with-no-code]] - Drew Breunig's article introducing `whenwords`, a spec-only library with tests and no implementation code.
- [[astral-uv]] - Astral's February 2024 launch post for `uv`, covering its `pip`/`pip-tools` compatibility, speed claims, resolver features, Rye stewardship, and "Cargo for Python" roadmap.
- [[codesandbox-homepage]] - CodeSandbox homepage positioning the product as isolated cloud sandbox infrastructure for AI agents, code execution, evals, CI/CD, and scaled development environments.
- [[fltman-loop-engineer]] - GitHub repository for a Claude Code skill and subagents that scaffold and audit guarded agentic loops.
- [[fumadocs-homepage]] - Fumadocs homepage positioning it as a composable React documentation framework with Markdown/MDX, headless customization, and flexible content sources.
- [[how-to-write-stuff-no-one-else-can]] - Ethan Brooks on building a writing moat through information advantage, overlooked sources, company timeline mapping, and interview chaining.
- [[ilyaglow-dockerfiles-whatweb]] - Dockerfiles repository addendum pointing to an example WhatWeb Dockerfile for building an audited local container image.
- [[magnitudedev-magnitude]] - GitHub repository and docs for Magnitude, an Apache-2.0 local agent and inference runtime with hardware-aware local model selection.
- [[nabla-c0d3-sslyze]] - GitHub repository for SSLyze, a CLI and Python library for SSL/TLS configuration scanning and CI compliance checks.
- [[observable-2-0]] - Observable's February 2024 announcement of Observable Framework as a code-first static site generator for data apps, dashboards, and reports.
- [[pnpm-vs-npm-vs-yarn-vs-bun-2026]] - DEV/Pockit comparison of npm, Yarn, pnpm, and Bun as JavaScript package managers in early 2026.
- [[rf-detr-docs]] - Roboflow RF-DETR documentation for a real-time detection transformer model family supporting detection, segmentation, and keypoint detection preview.
- [[urbanadventurer-whatweb]] - GitHub repository for WhatWeb, a web technology fingerprinting scanner useful for detecting exposed technology and version information.

## Entities

- [[astral]] - Python developer tooling company behind Ruff and `uv`.
- [[alejandro-piad-morffis]] - Author of the Mostly Harmless AI article on AI-assisted science as a loop.
- [[bun]] - JavaScript runtime with an integrated speed-focused package manager.
- [[claude-code]] - Host environment targeted by Loop Engineer; needs official-doc expansion before broad use.
- [[codesandbox]] - Platform for isolated cloud development environments, programmatic sandboxes, and secure code execution.
- [[drew-breunig]] - Author of the spec-only library article and creator of whenwords.
- [[ethan-brooks]] - Writer behind The Write to Roam, focused here on original research methods for writers.
- [[fumadocs]] - Open-source React documentation framework with composable content, core, and UI layers.
- [[loop-engineer]] - Claude Code skill/subagent pack for designing, scaffolding, teaching, and auditing guarded agent loops.
- [[magnitude]] - Open-source local agent and inference runtime with hardware-aware model selection, offline/private local model execution, skills, and OpenAI-compatible custom endpoints.
- [[mostly-harmless-ai]] - Alejandro Piad Morffis's AI publication.
- [[npm]] - Default package manager shipped with Node.js and baseline compatibility choice.
- [[observable]] - Data-visualization and data-app platform whose 2.0 direction separates exploratory notebooks from durable code-first data apps.
- [[observable-framework]] - Open-source static site generator for data apps, combining Markdown/JavaScript frontends with polyglot build-time data loaders.
- [[pnpm]] - JavaScript package manager focused on disk efficiency, strictness, and strong workspace support.
- [[rf-detr]] - Roboflow real-time detection transformer model family for object detection, instance segmentation, and keypoint detection preview.
- [[roboflow]] - Computer-vision platform company behind RF-DETR.
- [[uv]] - Rust-written Python package installer, resolver, virtual environment creator, and emerging project manager.
- [[rye]] - Experimental Python project manager that Astral took stewardship of as part of the `uv` roadmap.
- [[sslyze]] - SSL/TLS scanning CLI and Python library for certificates, ciphers, curves, protocol behavior, and known TLS attacks.
- [[stack-overflow]] - Developer Q&A and technical knowledge platform extending into agent-facing knowledge exchange.
- [[stack-overflow-for-agents]] - Beta API-first knowledge exchange for AI coding agents with human-reviewed publishing and verification feedback.
- [[the-write-to-roam]] - Ethan Brooks's writing site covering writing, newsletters, case studies, and research.
- [[together-ai]] - AI infrastructure company that CodeSandbox says it is now part of.
- [[whatweb]] - Web scanner that fingerprints website technologies, versions, headers, plugins, frameworks, and related cues.
- [[whenwords]] - Spec-only relative time formatting library distributed as specs and tests rather than implementation code.
- [[yarn]] - JavaScript package manager; Yarn 4/Berry emphasizes Plug'n'Play, zero-installs, and plugins.

## Concepts

- [[agent-loop-guardrails]] - Controls that keep autonomous agent loops bounded, verifiable, affordable, sandboxed, and human-gated.
- [[agent-knowledge-sharing]] - Letting agents reuse, contribute, and verify shared operational knowledge instead of rediscovering fixes in isolated sessions.
- [[ai-in-science]] - AI participation in scientific discovery workflows, especially candidate generation plus independent verification.
- [[build-time-data-loaders]] - Preparing dashboard data during build as static snapshots to improve performance, reduce source-system exposure, and simplify static deployment.
- [[python-packaging]] - Tooling and standards around Python dependency metadata, resolution, installation, virtual environments, and project management.
- [[cloud-development-environments]] - Remote development workspaces that can provide reproducible setup, shared compute, and controlled lifecycle.
- [[data-apps]] - Durable interactive applications for presenting, exploring, or communicating data, distinct from exploratory notebooks.
- [[dependency-resolution]] - Selecting package versions that satisfy project, transitive, and runtime constraints.
- [[detection-transformers]] - Transformer-based object detection architectures, including RF-DETR.
- [[documentation-frameworks]] - Reusable systems for docs-site routing, navigation, search, theming, content loading, and authoring.
- [[external-web-security-scanning]] - First-pass outside-in assessment of exposed web technologies, version clues, TLS posture, certificates, and weak configurations.
- [[information-advantage]] - Competitive edge from knowing useful things competitors do not.
- [[javascript-monorepo-package-management]] - Dependency and workspace management across multi-package JavaScript repositories.
- [[javascript-package-management]] - Installing, resolving, locking, auditing, and running dependencies in JavaScript/Node.js projects.
- [[javascript-package-manager-selection]] - Choosing between npm, Yarn, pnpm, and Bun based on project constraints.
- [[instance-segmentation]] - Computer-vision task that returns per-object masks rather than only bounding boxes.
- [[loop-engineering]] - Designing the control loop around an agent: triggers, verification, stopping conditions, budgets, and handoff.
- [[local-agent-inference]] - Running agent workflows on local models with hardware-aware model selection, quantization/context tradeoffs, model lifecycle management, and privacy/offline constraints.
- [[mdx-documentation]] - Documentation authoring that combines Markdown prose with JSX components and JavaScript expressions.
- [[outdated-software-exposure]] - Risk from exposed old CMS, plugin, library, framework, or server versions with known vulnerabilities.
- [[object-detection]] - Computer-vision task of identifying object instances with bounding boxes and class labels.
- [[proposer-verifier-curator-loop]] - Loop model where humans pose questions, AI proposes candidates, independent verifiers filter, and humans curate.
- [[sandboxed-code-execution]] - Running untrusted, generated, or user-submitted code inside isolated environments.
- [[source-discovery-for-writing]] - Finding people, documents, and traces that produce original material for writing.
- [[spec-driven-ai-development]] - Workflow where humans specify behavior, tests, and constraints while coding agents generate implementation code.
- [[spec-only-libraries]] - Libraries distributed as specs, tests, and implementation instructions instead of maintained source code.
- [[tls-compliance-in-ci]] - Automated TLS policy checks in CI/CD using profiles such as Mozilla old/intermediate/modern or custom configs.
- [[tls-configuration-scanning]] - Checking server TLS versions, certificates, ciphers, curves, extensions, and known TLS attack exposure.
- [[verification-driven-agent-knowledge]] - Agent knowledge model where value comes from repeated real-world verification rather than generation alone.
- [[verifier-bottleneck]] - Constraint that appears when cheap candidate generation outpaces reliable verification capacity.
- [[web-technology-fingerprinting]] - Identifying a website's visible software stack from responses, headers, paths, assets, and errors.
- [[interview-chaining]] - Expanding a source network by asking each interviewee who else should be consulted.

## Opinions

- [[ai-developer-tools]] - Working opinions on AI developer tools, currently including spec-driven AI development and loop engineering as hypotheses to evaluate.
- [[web-tools]] - Working opinions on practical web tooling, currently including external web security scanning and pnpm as the default JavaScript package manager recommendation.

## Comparisons

No comparison pages yet.
