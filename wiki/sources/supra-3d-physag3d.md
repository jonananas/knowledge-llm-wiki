---
type: source
tags: [computer-vision, 3d-generation, simulation, ai-agents]
updated: 2026-11-02
source_url: https://github.com/Supra-3D/PhysAg3D
---

# Supra-3D/PhysAg3D

Source: [GitHub repository README](https://github.com/Supra-3D/PhysAg3D), viewed 2026-11-02. Raw capture: [raw/supra-3d-physag3d.md](../../raw/supra-3d-physag3d.md).

## Summary

The repository presents [[physag3d]] as a workflow for [[image-to-interactive-3d|turning a single image into an interactive 3D asset]]. A 3D generator supplies detailed geometry and appearance; a vision-language agent infers parts and interactions, constructs physical structure, binds it to the generated surfaces, and uses rendered and execution evidence to refine the result.

## Key Takeaways

- **Appearance and interaction are separate but coupled.** The textured whole-object mesh and agent-proposed mechanisms begin from the same image. A hierarchical representation connects semantic intent, physical parts, and surface bindings so an interactive result can retain useful generated detail.
- **The agent uses geometric and simulation tools.** It builds articulated parts, joints, and compliant regions, then revises them using observed renders and execution measurements within a fixed case budget.
- **The release requires substantial external infrastructure.** The documented controller uses Blender and Codex CLI; a separate NVIDIA host runs TRELLIS.2 and other predeployed model dependencies. The repository does not ship their weights or a complete clean-install environment.
- **Delivery reports distinguish evidence levels.** `delivery.json` records output paths, interaction and physics status, motion kind, and limitations. Simulated replay, parameterized animation, and static output are different outcomes; a completed worker run is not automatically a physically validated asset.
- **Reproducibility has explicit boundaries.** File checksums and external fingerprints establish source/runtime identity, not visual quality or physical correctness. The protocol declares historical code references and `strict_isolation=false`; hidden mechanisms and material properties remain estimates from a single image.

## Implementation Notes

The `main` branch includes `execute.py`, example runtime profiles, method references, tests, source checksums, and external-runtime provenance. Its default case budget is three hours with at most two acceptance passes and two repair rounds. The README says the launcher currently requires `gpt-6-astra` at high reasoning effort; this is a release-specific requirement, not a general statement about the model.

## Connections

- [[physag3d]] — project and released workflow.
- [[image-to-interactive-3d]] — broader task and the inference limitations of a single view.
- [[gpt-6-astra]] — model required by the documented controller profile.
- [[agent-loop-guardrails]] — bounded revisions and explicit delivery status illustrate verification beyond a process exit code.

## Follow-ups

- [ ] [PhysAg3D paper](https://arxiv.org/abs/2610.39924) — inspect benchmark design, baselines, ablations, and the evidence for physical interaction claims.
- [ ] [PhysAg3D project page](https://supra-3d.github.io/PhysAg3D/) — inspect the gallery and distinguish qualitative demos from aggregate evaluation.
