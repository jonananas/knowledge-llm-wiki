# RF-DETR Docs

Source URL: https://rfdetr.roboflow.com/latest/
Source type: documentation homepage
Captured: 2026-08-26

RF-DETR is Roboflow's real-time transformer architecture for object detection, instance segmentation, and keypoint detection preview. The documentation positions it as a state-of-the-art accuracy-latency model family built on a DINOv2 vision transformer backbone.

## Main Points

- RF-DETR stands for Roboflow Detection Transformer.
- The model family supports object detection, instance segmentation, and keypoint detection preview through a consistent Python API.
- The architecture uses a DINOv2 vision transformer backbone.
- The docs say RF-DETR-L reaches 56.5 AP50:95 on COCO at 6.8 ms on an NVIDIA T4 using TensorRT FP16.
- The docs say RF-DETR-2XL reaches 60.1 AP50:95 on COCO at 17.2 ms and is the first real-time model to exceed 60 AP on COCO.
- RF-DETR was accepted at ICLR 2026.
- Authors listed in the documentation are Isaac Robinson, Peter Robicheaux, Matvei Popov, Deva Ramanan, and Neehar Peri.
- Core models from Nano through Large and all training/inference code are released under Apache 2.0.
- XLarge and 2XLarge detection models require `rfdetr[plus]` and are provided under PML 1.0.
- Installation requires Python 3.10 or later and can be done with `pip install rfdetr`, `uv pip install rfdetr`, or `uv add rfdetr`.
- The docs include tutorials for running detection models, segmentation models, keypoint models, training/fine-tuning, exporting, deployment, and benchmarking.
- Dataset formats include COCO JSON and YOLO-format datasets.
- Exports include ONNX and TensorRT; ONNX export works on CPU and TensorRT requires CUDA plus `rfdetr[tensorrt]`.
- The docs mention deployment to NVIDIA Jetson through Roboflow Inference.

## Benchmark Snapshot From The Homepage

Detection:

- RF-DETR-N: 48.4 COCO AP50:95, 2.3 ms latency, 30.5M params, 384x384 resolution.
- RF-DETR-S: 53.0 COCO AP50:95, 3.5 ms latency, 32.1M params, 512x512 resolution.
- RF-DETR-M: 54.7 COCO AP50:95, 4.4 ms latency, 33.7M params, 576x576 resolution.
- RF-DETR-L: 56.5 COCO AP50:95, 6.8 ms latency, 33.9M params, 704x704 resolution.
- RF-DETR-XL: 58.6 COCO AP50:95, 11.5 ms latency, 126.4M params, 700x700 resolution.
- RF-DETR-2XL: 60.1 COCO AP50:95, 17.2 ms latency, 126.9M params, 880x880 resolution.

Segmentation:

- RF-DETR-Seg-N: 40.3 COCO AP50:95, 3.4 ms latency.
- RF-DETR-Seg-S: 43.1 COCO AP50:95, 4.4 ms latency.
- RF-DETR-Seg-M: 45.3 COCO AP50:95, 5.9 ms latency.
- RF-DETR-Seg-L: 47.1 COCO AP50:95, 8.8 ms latency.
- RF-DETR-Seg-XL: 48.8 COCO AP50:95, 13.5 ms latency.
- RF-DETR-Seg-2XL: 49.9 COCO AP50:95, 21.8 ms latency.

Keypoints:

- RF-DETR Keypoint Preview: 71.8 COCO AP50:95, 9.7 ms latency, 40.7M params, 576x576 resolution.

## Notable Links From The Docs

- GitHub repository: https://github.com/roboflow/rf-detr
- RF-DETR paper link: https://arxiv.org/abs/2511.09554
- Install page: https://rfdetr.roboflow.com/latest/install/
- Benchmarks page: https://rfdetr.roboflow.com/latest/benchmarks/
- Roboflow: https://roboflow.com/
