---
type: concept
tags: [computer-vision, ai, transformers, object-detection]
updated: 2026-08-26
---

# Detection Transformers

Detection transformers are object-detection architectures that use transformer-based representations or decoders for detection tasks, rather than relying only on convolutional detector families.

The [[rf-detr-docs]] source presents [[rf-detr]] as a real-time detection transformer built on a DINOv2 vision transformer backbone. Its significance in the docs is the claimed combination of transformer-based accuracy with deployment-oriented latency.

## Why They Matter

Detection transformers are relevant when teams want strong representation learning and potential robustness to domain shift, while still needing real-time inference. The practical question is whether the accuracy gain justifies the training, export, deployment, and hardware constraints.

## Related Pages

- [[rf-detr]]
- [[object-detection]]
- [[instance-segmentation]]
