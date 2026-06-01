# SOD-YOLOv8-Small-Object-Detection
YOLOv8 enhanced with P2 detection head for small object detection on VisDrone2019  | Computer Vision Project
# SOD-YOLOv8: Small Object Detection for Autonomous Driving & Aerial Scenes
![Python](https://img.shields.io/badge/Python-3.12-blue)
![YOLOv8](https://img.shields.io/badge/YOLOv8-v8.3.0-green)
![Dataset](https://img.shields.io/badge/Dataset-VisDrone2019-orange)
![Platform](https://img.shields.io/badge/Platform-Google%20Colab-yellow)
##  Project Overview
Implementation of **SOD-YOLOv8** based on the research paper:
> Khalili & Smyth, *"SOD-YOLOv8: Enhancing YOLOv8 for Small Object Detection
> in Aerial Imagery and Traffic Scenes"*, MDPI Sensors, 2024.
> DOI: [10.3390/s24196209](https://doi.org/10.3390/s24196209)
Standard YOLOv8 misses small objects (pedestrians, cyclists) in drone footage
because its finest feature map is 80×80. SOD-YOLOv8 adds a **4th detection
head at P2 (160×160)** to detect objects as small as 8×8 pixels.

---

##  Academic Info
| Field | Details |
|---|---|
| University | National University of Modern Languages (NUML), Islamabad |
| Department | BS Artificial Intelligence |
| Subject | Computer Vision |
| Session | Spring 2026 |
| Student | Manahil Fatima |
| Roll No | BSAI-225 |
| Group | 10 |

---

##  Key Contributions of the Paper
- **P2 Detection Head (160×160)** — detects objects as small as 8×8 px
- **C2f-EMA Module** — Efficient Multi-Scale Attention for small object focus
- **PIoU Loss Function** — better bounding box precision for tiny objects

---

##  Results on VisDrone2019

| Model | mAP@50 | mAP@50-95 | Precision | Recall | FPS |
|---|---|---|---|---|---|
| Baseline YOLOv8s (50 ep) | 0.2648 | 0.1452 | 0.4086 | 0.2673 | 50.6 |
| SOD-YOLOv8s (20 ep) | 0.1968 | 0.1015 | 0.2858 | 0.2230 | **60.9** |

>  SOD-YOLOv8 trained for 20 epochs only due to Colab GPU memory limits.
> Paper reports 3–5% mAP@50 improvement at full 50-epoch training.

---

## 📂 Dataset
**VisDrone2019** — drone footage from 14 cities across China
- Training: 6,471 images
- Validation: 548 images
- Classes: pedestrian, people, bicycle, car, van, truck,
           tricycle, awning-tricycle, bus, motor
- ~69% of all objects are small (area < 32×32 px)

---

##  How to Run

### 1. Open in Google Colab
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1rgo1cRl3yQz4pCP3OWyg4HDAW_QIcfpS?usp=sharing)

### 2. Run cells in order
- Cell 1 — Environment Setup (restart session after this)
- Cell 2 — Imports
- Cell 3 — Download VisDrone2019
- Cell 4 — Convert Annotations to YOLO format
- Cell 5 — Exploratory Data Analysis
- Cell 8 — SOD-YOLOv8 Architecture Definition
- Cell 9 — Train Baseline YOLOv8s
- Cell 10 — Train SOD-YOLOv8s
- Cell 11 — Evaluate & Compare Both Models
- Cell 17 — Live Demo

---

## ⚙️ Tech Stack
| Component | Details |
|---|---|
| Framework | Ultralytics YOLOv8 v8.3.0 |
| Platform | Google Colab T4 GPU (15 GB) |
| Language | Python 3.12 |
| Deep Learning | PyTorch 2.x + CUDA |
| Visualization | Matplotlib, Seaborn, OpenCV |

---

## 🔗 Links
| Resource | Link |
|---|---|
| Research Paper | https://doi.org/10.3390/s24196209 |
| Dataset | https://github.com/ultralytics/ultralytics |

---

## 📜 Reference
Khalili, B., & Smyth, A. W. (2024). SOD-YOLOv8 — Enhancing YOLOv8 for
Small Object Detection in Aerial Imagery and Traffic Scenes.
*MDPI Sensors*, 24(19), 6209.
