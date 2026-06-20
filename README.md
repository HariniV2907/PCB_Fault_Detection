# 🔍 PCB Fault Detection Using YOLOv8

## 📄 Project Overview

Printed Circuit Boards (PCBs) are critical components in modern electronic devices, and even minor defects can lead to product failures, increased manufacturing costs, and reduced reliability. Traditional manual inspection methods are often time-consuming, labor-intensive, and prone to human error.

This project leverages **YOLOv8 (You Only Look Once)**, a state-of-the-art object detection algorithm, to automatically detect and classify PCB defects in real time. The system identifies multiple fault types with high accuracy, enabling faster quality assurance and improved manufacturing efficiency.

---

## 🎯 Objective

The primary objectives of this project are to:

* Detect and classify PCB defects with high accuracy.
* Identify common fault types such as:

  * Missing Holes
  * Mouse Bites
  * Shorts
  * Spurs
  * Open Circuits
  * Spurious Copper
* Enable real-time fault detection during the manufacturing process.
* Improve quality control and reduce defective products.
* Minimize inspection time compared to traditional manual inspection methods.
* Enhance overall product reliability and customer satisfaction.

---

## 📊 Dataset Description

The model was trained using annotated PCB images collected from publicly available datasets and repositories such as:

* Kaggle
* RoboFlow

### Defect Classes

| Class           | Description                              |
| --------------- | ---------------------------------------- |
| Missing Hole    | Missing drilled holes on PCB             |
| Mouse Bite      | Unwanted edge damage on PCB tracks       |
| Short           | Unintended connection between conductors |
| Spur            | Small unwanted copper protrusions        |
| Open Circuit    | Broken electrical connections            |
| Spurious Copper | Unwanted copper regions on PCB           |

The dataset contains images captured under varying conditions to improve model robustness and generalization.

---

## 🤖 Model Development

### YOLOv8 Architecture

The project utilizes **YOLOv8**, an advanced real-time object detection framework known for:

* High detection accuracy
* Fast inference speed
* Efficient feature extraction
* Real-time deployment capabilities

### Training Workflow

* Dataset collection and preprocessing
* Image annotation
* Dataset splitting (Train, Validation, Test)
* YOLOv8 model training
* Model evaluation and validation
* Real-time defect detection testing

---

## 📈 Results and Performance

The trained YOLOv8 model achieved strong performance in detecting and localizing PCB defects.

### Key Outcomes

* Accurate fault classification across multiple defect categories.
* High precision and recall for defect identification.
* Reliable defect localization using bounding boxes.
* Significant reduction in inspection time compared to manual methods.
* Improved consistency and repeatability in quality inspection.

### Benefits

* Faster manufacturing quality checks.
* Reduced production errors.
* Improved product reliability.
* Scalable deployment in industrial environments.

---

## 🛠️ Technologies Used

* Python
* YOLOv8
* Ultralytics
* PyTorch
* OpenCV
* NumPy
* Matplotlib

---

## 🚀 Installation

### Create Virtual Environment

```bash
conda create -n pcb_detection python=3.10
conda activate pcb_detection
```

### Install Dependencies

```bash
pip install ultralytics
pip install torch torchvision torchaudio
```

### Verify Installation

```bash
yolo checks
```

---

## 📂 Dataset Configuration

Create a YAML configuration file containing:

```yaml
path: dataset

train: images/train
val: images/val
test: images/test

names:
  0: missing_hole
  1: mouse_bite
  2: short
  3: spur
  4: open_circuit
  5: spurious_copper
```

---

## ▶️ Model Training

Train the YOLOv8 model using:

```bash
yolo detect train model=yolov8n.pt data=pcb.yaml epochs=100 imgsz=640
```

---

## 🔍 Model Inference

Run defect detection on images:

```bash
yolo detect predict model=runs/detect/train/weights/best.pt source=test_image.jpg
```

---

## 💡 Applications

* Electronics Manufacturing
* Automated Quality Inspection
* PCB Production Lines
* Industrial Automation
* Smart Manufacturing Systems

---

## 🚀 Future Enhancements

* Deployment using Streamlit or Flask.
* Integration with industrial cameras.
* Real-time video-based PCB inspection.
* Edge deployment using embedded devices.
* Defect severity classification.
* Integration with Industry 4.0 manufacturing systems.

---

## 🏁 Conclusion

This project demonstrates the effectiveness of YOLOv8 for automated PCB defect detection and classification. By replacing manual inspection with an AI-powered solution, manufacturers can improve quality assurance, reduce inspection time, and increase production efficiency. The system provides a scalable and reliable approach for modern electronics manufacturing environments.
