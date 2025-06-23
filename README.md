
# Evaluating Deep Learning-Based Panoptic Segmentation on RGB-Generated LiDAR Images

This repository contains the evaluation pipeline, inference code, and result summaries for a comparative study of several deep learning models on RGB images synthesized from LiDAR data.

## Thesis Title
**Evaluating Deep Learning-Based Panoptic Segmentation on RGB-Generated LiDAR Images**

---

##  Models Evaluated

| Model            | Type                 | Purpose / Notes |
|------------------|----------------------|------------------|
| **Mask2Former**  | Panoptic (Transformer) | Strong instance-aware baseline |
| **YOLOv5-Seg**   | Semantic/Instance     | Extended to panoptic via fusion |
| **DeepLabV3+**   | Semantic Only         | Simulated panoptic via connected components |
| **Detectron2**   | Panoptic              | COCO-trained model tested on LiDAR RGB |
| **UPSNet**       | Panoptic              | ResNet-50 backbone, tested on RGB LiDAR |

---

##  Structure

```bash
├── deeplabv3_panoptic_eval.ipynb     # Colab notebook with simulated panoptic evaluation
├── mask2former_eval.ipynb            # Inference + PQ metrics on LiDAR RGB image
├── yolov5_seg_eval.ipynb             # YOLOv5-Seg segmentation + fusion
├── detectron2_eval.ipynb             # Baseline Detectron2 panoptic evaluation
├── upsnet_eval.ipynb                 # UPSNet inference (WIP)
├── images/                           # Input and output visualizations
├── evaluation/                       # Evaluation utilities (PQ, RQ, SQ, mIoU)
└── README.md                         # This file
```

---

## Metrics Used

- **Panoptic Quality (PQ)**
- **Segmentation Quality (SQ)**
- **Recognition Quality (RQ)**
- **Mean Intersection over Union (mIoU)**

---

##  Key Findings

- DeepLabV3+ is ineffective for panoptic segmentation due to lack of instance awareness.
- Mask2Former and Detectron2 models perform more robustly on RGB-LiDAR input.
- Simulated instance labeling is feasible for semantic models, but recognition accuracy suffers.
- Domain shift from real-world RGB to LiDAR-generated RGB affects model performance.

---

## Dataset Format

All evaluations were conducted on **RGB images generated from LiDAR** scenes, with corresponding **semantic masks**.  
Panoptic ground truth was simulated via connected components where true instance annotations were unavailable.

---

## Requirements

Notebooks are tested in **Google Colab** with CPU-only compatibility where possible.

---

##  Contact

For academic questions or collaboration:
**[Sileshi Adal]**  
sileshi.ziena@gmail.com
siziada@utu.fi  
*Based on MSc Thesis, 2025*
