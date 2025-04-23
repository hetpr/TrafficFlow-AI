# 🚦 AI-Powered Adaptive Traffic Light System

An intelligent traffic management solution that dynamically adjusts traffic light timings using real-time video data and machine learning. This system aims to reduce congestion, optimize traffic flow, and support smarter, more efficient urban mobility.

---

## 📌 Overview

Traditional traffic light systems are often static and unable to adapt to real-time traffic conditions, resulting in congestion, long wait times, and increased emissions. Our project uses **Artificial Intelligence** and **Computer Vision** to enable **dynamic and responsive traffic control** by adapting signal timings based on live traffic data.

---

## 🎯 Objectives

- Monitor real-time traffic conditions using computer vision.
- Dynamically optimize traffic light timings based on traffic density.
- Reduce average waiting time and overall congestion.
- Support data-driven urban planning through traffic analytics.

---

## 🛠️ System Architecture

### A. Data Ingestion
- CSV-based traffic datasets for model training.
- Traffic junction videos (e.g., `junction_1.mp4`, `junction_2.mp4`).

### B. Preprocessing
- Encodes categorical inputs (`Low`, `Medium`, `High`) into numeric form.
- One-hot encoding for model targets.

### C. Neural Network (Model 1)
- **Framework:** TensorFlow / Keras
- **Architecture:**  
  `Input → Dense(64) → Dropout(0.2) → Dense(32) → Dropout(0.2) → Dense(16) → Output(Softmax)`
- **Purpose:** Predict which lane should get the green signal (1 to 4) based on traffic levels.

### D. Object Detection (Model 2)
- **Framework:** Ultralytics YOLOv8
- **Model:** Pre-trained `yolov8n.pt`
- **Purpose:** Detect and classify vehicles to determine traffic level.

### E. Logging and Data Storage
- **CSV Logs:** Traffic stats, decision outcomes, timestamps.

### F. Decision Logic
- Considers the 19 most recent traffic states.
- Outputs optimal green signal lane prediction.

### G. Visualization
- Uses `matplotlib` to overlay detection and traffic level data on video frames.

---

## 📊 Key Features

- 🔍 **Real-time vehicle detection** using YOLOv8.
- 🧠 **ML-based adaptive signal control** using deep learning.
- 🗂️ **Comprehensive logging** for traffic analytics and audit.
- 🔄 **Scalable and trainable architecture** for broader deployment.

---

## ✅ Results

- High accuracy in traffic detection and classification.
- Intelligent green-light lane predictions using ML.
- End-to-end decision cycle completes in seconds.
- Logs provide full traceability for real-time and historical analysis.

---

## 🌍 Benefits

- **Improved Traffic Flow:** Faster decisions, less congestion.
- **Time-Saving:** Automated control reduces manual traffic direction.
- **Urban Planning Support:** Data logs enable better infrastructure decisions.
- **Reduced Emissions:** By minimizing idling and wait times.

---

## 🚀 Future Enhancements

- Scale to handle large real-time datasets more efficiently.
- Enhance model accuracy using context-aware learning.
- Integrate with smart city infrastructure (sensors, public transit, etc.).

---

## 🧠 Technologies Used

- Python
- TensorFlow / Keras
- YOLOv8 (Ultralytics)
- OpenCV
- Matplotlib
- CSV, NumPy, OS, Datetime libraries
