# PCB Defect Detection Using YOLOv8

## Overview

This project presents an end-to-end deep learning solution for automated Printed Circuit Board (PCB) defect detection using YOLOv8. The objective is to identify and localize manufacturing defects in PCB images, enabling faster, more reliable, and scalable quality inspection compared to traditional manual methods.

The project is designed as a hands-on educational lab that introduces students to modern computer vision and industrial AI applications.

---

## Problem Statement

Printed Circuit Boards (PCBs) are critical components in electronic devices. During manufacturing, defects such as open circuits, short circuits, pinholes, and spurs can occur, impacting product reliability and performance.

Traditional visual inspection is often:

- Time-consuming
- Labor-intensive
- Prone to human error

This project addresses the challenge of automatically detecting PCB defects from images using deep learning-based object detection techniques.

---

## Defect Categories

The model is trained to detect the following PCB defects:

- Open Circuit
- Short Circuit
- Mouse Bite
- Spur
- Pin Hole
- Copper Defect

---

## Learning Objectives

After completing this project, students will be able to:

- Understand object detection fundamentals
- Work with annotated datasets
- Train and evaluate YOLOv8 models
- Interpret detection metrics
- Perform inference on unseen images
- Apply AI techniques to industrial inspection problems

---

## Dataset Structure

```text
dataset/
├── train/
│   ├── images/
│   └── labels/
│
├── valid/
│   ├── images/
│   └── labels/
│
└── test/
    ├── images/
    └── labels/
```

Each image has a corresponding YOLO-format annotation file containing defect locations and class labels.

---

## Technology Stack

- Python
- PyTorch
- YOLOv8 (Ultralytics)
- OpenCV
- NumPy
- Matplotlib
- Jupyter Notebook

---

## Installation

### Clone the Repository

```bash
git clone https://github.com/your-username/pcb-defect-detection-yolov8.git
cd pcb-defect-detection-yolov8
```

### Install Dependencies

```bash
pip install ultralytics
pip install opencv-python numpy matplotlib pandas
```

---

## Project Workflow

### 1. Dataset Preparation

- Organize images and labels
- Verify dataset structure
- Configure `data.yaml`

### 2. Data Exploration

- Visualize PCB images
- Inspect annotations
- Analyze defect distribution

### 3. Model Training

Train a YOLOv8 model to learn defect patterns from annotated PCB images.

```python
from ultralytics import YOLO

model = YOLO("yolov8n.pt")

model.train(
    data="data.yaml",
    epochs=50,
    imgsz=640,
    batch=8
)
```

### 4. Model Evaluation

Evaluate performance using:

- Precision
- Recall
- mAP@50
- mAP@50-95

### 5. Defect Detection

Run inference on unseen PCB images.

```python
from ultralytics import YOLO

model = YOLO("best.pt")

results = model.predict(
    source="sample.jpg",
    conf=0.25
)
```

The model outputs:

- Defect category
- Confidence score
- Bounding box coordinates

---

## Sample Output

The trained model automatically:

- Detects PCB defects
- Draws bounding boxes around defective regions
- Labels each defect with its predicted class
- Reports confidence scores

---

## Applications

- Electronics Manufacturing
- Automated Optical Inspection (AOI)
- Quality Assurance Systems
- Smart Manufacturing
- Industry 4.0 Solutions

---

## Future Enhancements

- Real-time video-based defect detection
- Edge AI deployment
- ONNX/TensorRT optimization
- Web-based inspection dashboard
- Additional PCB defect classes

---

## Repository Structure

```text
pcb-defect-detection-yolov8/
│
├── dataset/
├── models/
├── results/
├── notebooks/
├── data.yaml
├── requirements.txt
└── README.md
```

---

## Acknowledgements

This project is developed as an educational laboratory exercise to demonstrate the application of deep learning and computer vision in automated industrial quality inspection.

---

## License

This project is intended for educational and research purposes.
