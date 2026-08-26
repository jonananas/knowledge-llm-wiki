---
type: source
tags: [computer-vision, object-detection, ai, roboflow]
updated: 2026-08-26
source_url: https://rfdetr.roboflow.com/latest/
---

# RF-DETR Docs

Source: [RF-DETR documentation](https://rfdetr.roboflow.com/latest/). Raw capture: [raw/rf-detr-docs.md](../../raw/rf-detr-docs.md).

## Summary

The RF-DETR documentation presents [[rf-detr]] as [[roboflow]]'s real-time transformer architecture for [[object-detection]], [[instance-segmentation]], and keypoint detection preview. It uses a DINOv2 vision transformer backbone and is positioned around state-of-the-art accuracy-latency tradeoffs.

The docs describe RF-DETR as accepted at ICLR 2026 and list Isaac Robinson, Peter Robicheaux, Matvei Popov, Deva Ramanan, and Neehar Peri as authors. Core models from Nano through Large and the training/inference code are Apache 2.0; XLarge and 2XLarge detection models require `rfdetr[plus]` and use PML 1.0.

## Key Takeaways

- RF-DETR is a [[detection-transformers]] model family for real-time computer vision.
- It supports detection, segmentation, and preview keypoint detection through one Python API.
- Installation requires Python 3.10 or newer and supports `pip`, `uv pip`, and `uv add`.
- The docs claim RF-DETR-L reaches 56.5 COCO AP50:95 at 6.8 ms on NVIDIA T4 with TensorRT FP16.
- The docs claim RF-DETR-2XL reaches 60.1 COCO AP50:95 at 17.2 ms, which they frame as the first real-time model to exceed 60 AP on COCO.
- Dataset formats include COCO JSON and YOLO-format datasets.
- Export targets include ONNX and TensorRT.
- The docs point to deployment workflows including NVIDIA Jetson through Roboflow Inference.
- Licensing is split: Apache 2.0 for core code/models through Large, PML 1.0 for XLarge and 2XLarge detection models.

## Model Sizes From The Homepage

Detection models range from RF-DETR-N at 2.3 ms / 48.4 COCO AP50:95 to RF-DETR-2XL at 17.2 ms / 60.1 COCO AP50:95. Segmentation models range from RF-DETR-Seg-N at 3.4 ms / 40.3 AP50:95 to RF-DETR-Seg-2XL at 21.8 ms / 49.9 AP50:95. The keypoint preview model reports 71.8 COCO AP50:95 at 9.7 ms.

These numbers are documentation claims from the homepage and should be checked against the benchmark methodology before using them for model selection.

## Connections

- [[rf-detr]] - central model family.
- [[roboflow]] - company behind the docs and model.
- [[object-detection]] - primary task.
- [[instance-segmentation]] - supported task.
- [[detection-transformers]] - architecture family.
- [[uv]] - installation path appears in the docs.

## Follow-ups

- [ ] [RF-DETR GitHub repository](https://github.com/roboflow/rf-detr) - capture implementation details, package structure, license files, and release history.
- [ ] [RF-DETR paper](https://arxiv.org/abs/2511.09554) - ingest the primary paper for architecture and benchmark methodology.
- [ ] [RF-DETR benchmarks page](https://rfdetr.roboflow.com/latest/benchmarks/) - preserve full competitor comparison and methodology.
- [ ] [Deploy RF-DETR to NVIDIA Jetson](https://blog.roboflow.com) - capture edge deployment path if useful later.
