# 🚦 Object Detection with YOLOv8

[![Ultralytics YOLOv8](https://img.shields.io/badge/Ultralytics-YOLOv8-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://github.com/ultralytics/ultralytics)
[![Python](https://img.shields.io/badge/Python-3.9+-blue.svg?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

This project implements a **custom multi-class object detection system** using **YOLOv8**, trained on a manually annotated dataset to detect:

> **🚗 Cars, 🚌 Buses, 🚚 Trucks, 🧍 People, and 🔢 Number Plates**

Built with Ultralytics' YOLOv8 Nano, this model is optimized for **low-VRAM GPUs** and runs smoothly on both **CPU and GPU environments**.

---

## 📁 Project Overview

- ✅ Custom multi-class dataset annotated using **Label Studio**
- 🔧 Trained using YOLOv8 Nano (`yolov8n.pt`)
- 🧠 Inference results are generated and saved to a folder
- 🎯 Optimized for performance on entry-level GPUs (like RTX 2050)

---

## 🚀 Features

- 📦 Multi-class detection: **number plates, cars, buses, trucks, people**
- 🧠 Powered by Ultralytics YOLOv8
- ⚙️ Supports both **CPU and GPU** execution
- 📁 Auto-saves predictions to `predicted_results/`
- 🧠 Optimized image size and batch size to prevent CUDA errors

---

## 🛠️ Installation

Install YOLOv8 and dependencies using pip:

```bash
pip install ultralytics
```

---

## 🏗️ Workflow Summary

### 1. 📸 Dataset Annotation
- Annotated using **Label Studio**
- Exported in YOLOv8-compatible format

### 2. 🧠 Model Training

| Parameter     | Value         |
|---------------|---------------|
| Model         | `yolov8n.pt`  |
| Epochs        | 150           |
| Image Size    | 640           |
| Batch Size    | 4             |
| Optimizer     | Adam          |
| Learning Rate | 0.001 (cosine decay) |
| Augmentations | HSV, RandAugment     |

> Trained using both CPU and GPU fallback to suit low-resource environments.

### 3. 🔍 Inference
Run predictions on random images and save results using:

```python
results = model("your_image.jpg")
results[0].save()
```

---

## 🧾 Classes Used

Listed in `classes.txt`:

```
0: number_plate
1: car
2: bus
3: truck
4: person
```

---

## 🖼️ Sample Outputs

Detected object bounding boxes are stored under:

```bash
predicted_results/
```

Use `results[0].show()` or `.save()` for visualization.

---

## 📂 Folder Structure

```bash
object_detection_project/
├── images/
├── labels/
├── weights/
│   └── best.pt
├── predicted_results/
├── number_plate_dataset.yaml
├── numberplateprediction.ipynb
├── classes.txt
└── README.md
```

---

## 🔮 Future Improvements

- 📊 Improve dataset quality, balance class distribution
- 🚀 Upgrade to `yolov8s.pt` for higher accuracy
- ✂️ Integrate license plate cropping + OCR module
- 🌐 Deploy with Flask or Streamlit for live inference

---

## 👤 Author

**Made by VP**  

---
