## 技術摘要

#### 資訊來源

- Title: Segment Anything
- 論文: https://scontent.ftpe8-2.fna.fbcdn.net/v/t39.2365-6/10000000_900554171201033_1602411987825904100_n.pdf?_nc_cat=100&ccb=1-7&_nc_sid=3c67a6&_nc_ohc=wNkFGThcmjwAb4N5Rbd&_nc_ht=scontent.ftpe8-2.fna&oh=00_AfAM_b3vi2wR6i2fuvZlon9T-WeeqovYVvd0tBr7e7_bgA&oe=662E9827
- Arxiv: https://arxiv.org/abs/2304.02643
- Github: https://github.com/facebookresearch/segment-anything

#### 發表資訊

- 發表期刊/會議: ICCV 2023
- arxiv 發表年月: 202304
- 作者所屬學校/機構: Meta AI Research, FAIR

#### 研究貢獻

- 研究目標背景知識: 開發基於大規模數據的強大零擊中(image segmentation)基礎模型，使用提示(prompt)進行訓練，以達到零擊中轉移到多個下游任務的能力。
- 研究目標: 建立一個可通過提示進行即時影像分割的基礎模型，並能夠在沒有進一步訓練的情況下適用於新的任務和數據分佈。
- 資料集描述: 使用名為SA-1B的數據集，包括超過11M張圖片和1B個掩碼，這些圖片和掩碼均已取得授權且尊重隱私。
- 關鍵發現: SAM（Segment Anything Model）可以從單一前景點提示中產生高質量的掩碼，這些掩碼的質量接近手動標註的地面真相。
- 研究結果比較: 與當前的基於完全監督學習的模型相比，SAM在多數資料集上的表現接近或超越這些模型，尤其是在零擊中設定中表現出色。

#### 模型

- 理論架構和設計: 本文提出一種新的基於提示的影像分割任務，透過提示工程來實現對新的任務和數據分佈的零擊中遷移。
- 模型資訊_architecture: Segment Anything Model (SAM)
- 模型資訊_backbone: 使用Vision Transformer (ViT)作為影像編碼器

#### 論文截錄

- Abstract: We introduce the Segment Anything (SA) project: a new task, model, and dataset for image segmentation. Using our efficient model in a data collection loop, we built the largest segmentation dataset to date (by far), with over 1 billion masks on 11M licensed and privacy respecting images. The model is designed and trained to be promptable, so it can transfer zero-shot to new image distributions and tasks. We evaluate its capabilities on numerous tasks and find that its zero-shot performance is impressive -- often competitive with or even superior to prior fully supervised results. We are releasing the Segment Anything Model (SAM) and corresponding dataset (SA-1B) of 1B masks and 11M images at this https URL to foster research into foundation models for computer vision.
- metrics & experiments:
- Architecture:
- contribution
- Ablation study
- conclusion & keywords(累積)

## Segment Anything with SAM

#### Introduction

This script allows users to perform object segmentation on images using different input methods like points, bounding boxes, or a combination of both with the SAM model.

#### Dependencies

- Python 3.8+
- NumPy
- Matplotlib
- OpenCV
- Torch
- torchvision
- segment_anything

#### Installation

Ensure you have the required dependencies:

```bash
pip install numpy matplotlib opencv-python torch torchvision
```

#### Examples

**Segment with Points**

```bash
python SAM.py --input_point '100,100;110,110;0,0' --input_label '1,1,0' --image_path './path/to/your/image.jpg'
```

**Segment with Bounding Box**

```bash
python SAM.py --input_box '10,100,300,300' --image_path './path/to/your/image.jpg'
```

**Segment with Points and Bounding Box**

```bash
python SAM.py --input_point '100,100;110,110;0,0' --input_label '1,1,0' --input_box '10,100,300,300' --image_path './path/to/your/image.jpg'
```
