---
type: concept
tags: [computer-vision, ai, segmentation]
updated: 2026-08-26
---

# Instance Segmentation

Instance segmentation is a computer-vision task where a model identifies individual object instances and returns a mask for each object, rather than only a bounding box.

The [[rf-detr-docs]] source says RF-DETR-Seg models extend the RF-DETR family to instance segmentation while sharing the backbone and training API. The docs note that segmentation adds a mask head and requires COCO-format segmentation annotations.

## Related Pages

- [[rf-detr]]
- [[object-detection]]
- [[detection-transformers]]
