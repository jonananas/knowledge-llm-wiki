---
type: entity
tags: [computer-vision, object-detection, ai, roboflow]
updated: 2026-08-26
---

# RF-DETR

RF-DETR is Roboflow's real-time detection transformer model family for [[object-detection]], [[instance-segmentation]], and keypoint detection preview. The docs say it uses a DINOv2 vision transformer backbone and was accepted at ICLR 2026. [[rf-detr-docs]]

## Role

RF-DETR is positioned as a practical alternative to YOLO-style detectors when accuracy-latency tradeoff and domain-shift performance matter. The documentation emphasizes deployment as well as training: pretrained inference, fine-tuning, export to ONNX/TensorRT, and edge deployment workflows.

## Model Family

- Detection: Nano, Small, Medium, Large, XLarge, and 2XLarge.
- Segmentation: Seg Nano, Seg Small, Seg Medium, Seg Large, Seg XLarge, and Seg 2XLarge.
- Keypoints: Keypoint Preview for COCO person keypoints.

## Licensing

Core models from Nano through Large and all training/inference code are Apache 2.0 according to the docs. XLarge and 2XLarge detection models require `rfdetr[plus]` and are under PML 1.0. [[rf-detr-docs]]

## Related Pages

- [[roboflow]]
- [[object-detection]]
- [[instance-segmentation]]
- [[detection-transformers]]

## Follow-ups

- [ ] [RF-DETR GitHub](https://github.com/roboflow/rf-detr) - verify repository structure, model weights, licenses, issues, and releases.
- [ ] [RF-DETR paper](https://arxiv.org/abs/2511.09554) - capture architecture, training data, and benchmark methodology.
