# Supra-3D/PhysAg3D

Source URL: https://github.com/Supra-3D/PhysAg3D
Primary source viewed: repository README on `main`
License: MIT for original PhysAg3D source; external models and tools have separate licenses
Captured: 2026-11-02

## Main Points

- PhysAg3D aims to turn one image into a textured 3D asset whose parts can move or deform plausibly. The README frames the problem as preserving the visual detail of a 3D generator while adding object-specific physical structure and interactions.
- A vision-language agent infers semantic parts, mechanisms, possible interactions, and physical priors. A pretrained 3D generator independently creates a textured whole-object mesh from the image.
- A hierarchical interaction representation links the agent's proposed behavior to physical parts and to the generated surfaces that should follow them. The agent builds joints and compliant regions, then binds those structures to the rendered mesh.
- The workflow observes rendered states and execution measurements and makes targeted revisions within a fixed budget. It supports rigid articulation and compliant deformation, but a single view leaves hidden structure, scale, and material properties underdetermined.
- The released `main` branch contains a controller/worker workflow rather than a turnkey model. `execute.py` verifies file identities, checks the environment, prepares a case, shows the launch command, and runs the worker. The repository also contains method references, example runtime profiles, example input images, tests, checksums, and external-runtime provenance.
- The documented default uses a Windows controller and separate Linux NVIDIA generation host. It needs Blender, a compatible Codex CLI with the user's own ChatGPT login, TRELLIS.2 and related native dependencies, and predeployed model weights. The example configuration checks for at least 28 GiB of free GPU memory. An experimental Linux-local profile is also provided.
- The launcher currently requires `gpt-6-astra` at high reasoning effort. A default case has a three-hour budget, at most two acceptance passes, and at most two repair rounds. Prepared inputs are checked before execution; previously attempted cases are not silently resumed or retried.
- The `delivery.json` contract records final assets and their limitations: refined GLB, editable Blender file, MuJoCo scene, motion evidence, comparisons, and a viewer when available. Its interaction and physics status distinguish simulated replay, parameterized animation, and static output. Worker completion alone is not proof that the asset passed physical checks.
- The README says source checksums and environment fingerprints verify identity, not visual or physical correctness. It also declares historical code-only examples and `strict_isolation=false`, so the release is an assisted workflow rather than a fully isolated inference demonstration.

## Notable Links

- Project page and gallery: https://supra-3d.github.io/PhysAg3D/
- Research paper: https://arxiv.org/abs/2610.39924
