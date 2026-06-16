# 🛡️ Aegis Vision

**Edge-to-Cloud Traffic Violation Identification Framework**

## 📖 Project Overview
Aegis Vision is an end-to-end, multi-modal deep learning architectural framework designed to automate the identification and classification of traffic violations across Bengaluru's massive camera infrastructure.

## ⚠️ The Challenge
Manual enforcement of traffic laws is computationally and humanly unscalable. Furthermore, passing unoptimized, continuous video feeds into heavy deep-learning networks results in:
1. **Massive cloud infrastructure costs** due to wasted compute on non-violating vehicles.
2. **High false-positive rates** caused by environmental degradation (e.g., severe nighttime headlight glare and heavy monsoons).

## 💡 The Solution
Aegis Vision solves these bottlenecks through a highly optimized **Hierarchical Edge-to-Cloud Pipeline** featuring our proprietary **Smart Trigger Engine**.

---

## 🚀 Key Technical Innovations

### 1. 🌦️ Robustness Layer (Image Preprocessing)
Raw camera feeds are heavily degraded by the environment. Aegis Vision implements **Zero-DCE** and **de-fogging CNNs** at the ingestion point to dynamically normalize nighttime headlight glare and monsoon conditions *before* the frames hit the inference engines.

### 2. 🧠 Multi-Head Classification
The framework utilizes dedicated, lightweight sub-networks isolated for specific infractions:
* **CNNs** for helmet non-compliance.
* **Instance Segmentation** for triple-riding detection.
* **DeepSORT Temporal Tracking** applied over static virtual polygons to capture dynamic infractions like red-light jumps, wrong-side driving, and illegal parking.

### 3. ⚙️ Smart Trigger Engine (Cost Optimization)
To eliminate wasted cloud compute, heavy inference sequences (such as ANPR/OCR using PaddleOCR) remain completely dormant. They are **ONLY** instantiated if the primary violation classification heads return an aggregate confidence score of `> 0.85`.

### 4. 🔒 Cryptographic Admissibility
For automated enforcement to be legally viable, evidence cannot be altered. All generated evidence packages (raw original image, annotated bounding boxes, and JSON metadata) are locked using **SHA-256 cryptographic hashing** and digital signatures to ensure 100% tamper-proof legal admissibility.

---

## 🛠️ Conceptual Tech Stack
* **Primary Detection:** YOLOv8 / YOLOv10
* **Tracking Engine:** DeepSORT / ByteTrack
* **Text Extraction (ANPR):** PaddleOCR (CRNN + CTC)
* **Image Restoration:** Zero-DCE, CLAHE, De-Fogging CNNs
* **Security:** SHA-256 Hashing Algorithms

## 👥 Team
* **Team:** 1-BIT
* **Lead Engineer:** Anil Kumar
* **Hackathon:** Flipkart Gridlock Hackathon 2.0 (Prototype Round 2)
