## Fire Detection

### 📌 Project Overview
This project develops a YOLOv8-based real-time fire detection system using a Roboflow-provided dataset. The pipeline involves dataset preprocessing, model training, threshold sweeping on validation/test sets, and deployment with webcam inference. Optimal thresholds are chosen to balance precision and recall for reliable fire detection in live video streams.

### 📂 Dataset Composition
**Source:** [Roboflow – continuous_fire](https://universe.roboflow.com/-jwzpw/continuous_fire)

- Train set: train/fire images

- Validation set: valid/fire images

- Test set: test/fire images

### ⚙️ Workflow

- Imports & Configurations – environment setup (Ultralytics 8.3.0, CUDA:0 MX450, Torch 2.0.1).

- Dataset & YAML – YOLO-format dataset with single class fire.

- Model Training – YOLOv8 with imgsz=320, val/test splits.

- Threshold Sweep – confidence thresholds (0.05, 0.425, 0.80) evaluated; metrics computed (P, R, F1, mAP50, mAP50–95).

- Optimal Threshold – selected conf=0.05, iou=0.55, based on validation F1/recall balance.

- Evaluation – performance measured on validation and test sets.

- Deployment – real-time webcam inference.

### 📊 Results

- Best Threshold: conf = 0.05, iou = 0.55  
- Validation: P=0.854, R=0.735, F1=0.790, mAP50=0.823, mAP50–95=0.570  
- Test: P=0.863, R=0.659, F1=0.747, mAP50=0.778, mAP50–95=0.543  

<table>
  <tr>
    <td align="center">
      <img src="https://github.com/user-attachments/assets/4e7c67a7-ccb8-4d63-86a7-a80e295146f5" width="400"><br>
      <sub>Validation Labels</sub>
    </td>
    <td align="center">
      <img src="https://github.com/user-attachments/assets/3ce338ff-34cb-4788-b1b4-108cc232b78d" width="400"><br>
      <sub>Webcam Inference</sub>
    </td>
  </tr>
</table>







