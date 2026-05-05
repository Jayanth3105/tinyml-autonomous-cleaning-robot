# Autonomous Cleaning Robot with TinyML-Based Debris Classification
<img width="1027" height="663" alt="Proper view" src="https://github.com/user-attachments/assets/20eafbe6-f111-49c3-be68-e9ac74c79917" />

## 🚀 Overview
This project presents an end-to-end autonomous cleaning robot capable of detecting and classifying debris (solid vs liquid) using a TinyML model deployed on embedded hardware.

The system integrates perception, decision-making, and actuation, enabling adaptive cleaning behavior in real-time under strict hardware constraints.

---

## 🧠 Key Contributions

- Deployment of deep learning model on **resource-constrained microcontroller (ESP32-CAM)**
- Real-time debris classification enabling adaptive cleaning actions
- Full robotics pipeline: perception → classification → decision → actuation
- Model optimization using pruning and quantization for edge deployment

---

## 🏗️ System Architecture

### Hardware
- Arduino Mega (main controller)
- ESP32-CAM (vision + ML inference)
- Ultrasonic sensor (obstacle detection)
- BLDC motor + ESC (locomotion)
- Servo motors (mechanism switching)
- Motor drivers (L298N / L293D)

### Software
- TensorFlow / Keras
- TensorFlow Lite
- Edge Impulse
- Arduino IDE

---
<img width="1340" height="753" alt="model architecture" src="https://github.com/user-attachments/assets/787be381-f11a-4366-af91-212ec89810f4" />

## 🤖 Robot Design


::contentReference[oaicite:2]{index=2}


- Dual-layer cylindrical chassis design
- Rotatable cleaning mechanism (vacuum + mop)
- Camera mounted on servo for debris detection
- Modular architecture for sensor and actuator integration
<img width="3509" height="2141" alt="CAD model" src="https://github.com/user-attachments/assets/dde1dabc-34d5-4ebd-8002-2114b41eb54a" />

---

## 🧠 Machine Learning Model

### Model
- MobileNetV2 (transfer learning)
- Binary classification: **Solid vs Liquid debris**

### Dataset
- ~220 images per class
- Data augmentation applied (rotation, scaling, flipping)

---

## 📊 Model Performance

### Before Optimization

::contentReference[oaicite:3]{index=3}


- Accuracy: **97.7%**
- Loss: 0.21
<img width="741" height="882" alt="Pre pruniing model" src="https://github.com/user-attachments/assets/e19d194c-8c24-48e5-b2e1-3a475c03c05e" />

---

### After Quantization (int8)

::contentReference[oaicite:4]{index=4}


- Accuracy: **~77.3%**
- Significant reduction in model size
- Enabled deployment on embedded hardware
<img width="732" height="863" alt="final_model" src="https://github.com/user-attachments/assets/d6ff85e2-119d-4795-9c51-d3b308afc1b5" />

---

## ⚙️ Model Optimization

- Pruning (TensorFlow Model Optimization Toolkit)
- Quantization-aware training
- TensorFlow Lite conversion
- Edge Impulse deployment pipeline

👉 Trade-off:
- ↓ Model size + latency  
- ↓ Accuracy (~20% drop)

---

## 🔌 Hardware Integration


::contentReference[oaicite:5]{index=5}


- ESP32-CAM performs image classification
- Arduino Mega controls motors and actuators
- Serial communication between modules
- Cleaning mechanism activated based on classification output

---

## ⚡ System Workflow

1. Capture image using ESP32-CAM  
2. Run TinyML inference  
3. Classify debris (solid / liquid)  
4. Send signal to Arduino  
5. Activate appropriate cleaning mechanism  
6. Continue navigation  


---

## 📄 Documentation

- 📘 Full Project Report: Included in repo  
- 📊 Presentation Slides: Included  

---

## ⚠️ Challenges

- Severe memory constraints (ESP32)
- Model compression vs accuracy trade-off
- Sensor noise and real-world variability
- Hardware integration complexity

---

## 🧠 Key Learnings

- TinyML deployment on microcontrollers  
- Model optimization (pruning + quantization)  
- Embedded AI systems design  
- End-to-end robotics system integration  

---

## 🎯 Future Work

- Improve accuracy under quantization
- Expand dataset
- Real-time navigation + SLAM integration
- Upgrade to more powerful edge hardware

---

## 🧠 Tech Stack

Python • TensorFlow • TensorFlow Lite • Edge Impulse  
Arduino • ESP32 • Embedded C  
Computer Vision • TinyML • Robotics
