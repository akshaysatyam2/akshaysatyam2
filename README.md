# Akshay Kumar

<div align="center">
  <a href="https://www.linkedin.com/in/akshaysatyam2/">
    <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white"/>
  </a>
  <a href="https://github.com/akshaysatyam2">
    <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white"/>
  </a>
  <a href="https://www.kaggle.com/akshaysatyam2">
    <img src="https://img.shields.io/badge/Kaggle-20BEFF?style=for-the-badge&logo=kaggle&logoColor=white"/>
  </a>
  <a href="https://twitter.com/akshaysatyam2">
    <img src="https://img.shields.io/badge/X-000000?style=for-the-badge&logo=x&logoColor=white"/>
  </a>
  <a href="https://akshaysatyam2.github.io/akshaysatyam2/">
    <img src="https://img.shields.io/badge/Portfolio-00C853?style=for-the-badge&logo=google-chrome&logoColor=white"/>
  </a>
</div>

<br/>

<div align="center">
  <img src="https://komarev.com/ghpvc/?username=akshaysatyam2&label=Profile+Views&color=7c3aed&style=flat-square"/>
</div>

---

## About Me

**Computer Vision Engineer | Data Engineer | ML Researcher**  
Real-time CV on edge devices • Scalable Data Pipelines • Deep Learning • MLOps  

Passionate about building production-grade solutions using **Data Engineering**, **Computer Vision**, and **Deep Learning**. Expertise in architecting high-performance pipelines and deploying AI at scale.

---

### GitHub Activity & Stats

<div align="center">

<!-- Reliable GitHub Stats -->
<img src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=akshaysatyam2&theme=tokyonight" alt="GitHub Stats" width="800"/>

<br/><br/>

<!-- Streak – the only host that never dies -->
<img src="https://streak-stats.demolab.com?user=akshaysatyam2&theme=tokyonight&hide_border=true&background=0d1117&stroke=7c3aed&ring=7c3aed&fire=ff6b6b&currStreakLabel=7c3aed&currStreakNum=7c3aed&sideNums=7c3aed&dates=8b9494"/>

</div>

---

## Skills

| Category                  | Technologies |
|---------------------------|------------|
| **Core ML/AI**            | Computer Vision • NLP • Deep Learning • LLMs • RAG |
| **Frameworks**            | TensorFlow • PyTorch • OpenCV • YOLO • Hugging Face • LangChain |
| **Languages**             | Python • SQL • Bash |
| **Tools & Platforms**      | Docker • Kafka • MQTT • FastAPI • Git • Linux • MediaPipe |
| **Cloud & Edge**          | AWS (Bedrock, Lambda) • Azure Edge • MLOps • CI/CD |

---

## Featured Projects

### 🐾 PupsN Vision System - AI-Powered Pet Analytics
**Tech Stack:** Python, YOLO26 Nano, OSNet, ONNX Runtime, OpenCV, Flask-SocketIO, HTML5 Canvas

Welcome to the PupsN Vision System. This project is a high-performance, edge-optimized implementation of a pet monitoring system featuring real-time detection, tracking, re-identification, and behavior classification.

<div align="center">
  <video src="Final_Demo_PupsN_Edge.mp4" width="100%" controls></video>
  <br/>
  <a href="Final_Demo_PupsN_Edge.mp4">📺 Click here to watch the full demo video</a>
</div>

#### 🏗️ System Architecture & Topology
To prevent frame drops and thread exhaustion, every camera stream is managed by two dedicated parallel threads:
- **stream_worker (Visual Layer):**
  - Continuously captures frames at native camera speeds.
  - Layers the latest available AI metadata (bounding boxes, names, behaviors) onto the frame.
  - Transmits a smooth 30 FPS stream to the frontend via WebSockets.
- **ai_worker (Inference Layer):**
  - Runs continuously at maximum CPU potential.
  - Performs YOLO detection, IoU Tracking, OSNet Re-ID, and Pose Classification.
  - Updates a shared memory state that the visual layer consumes asynchronously.

#### 🧠 AI Pipeline (ONNX Runtime)
The application utilizes `onnxruntime` with full graph optimizations to execute a 4-stage pipeline:
1. **Detection (YOLO26 Nano):** Identifies dogs in the frame with high precision (FP32).
2. **Persistent Tracking (IoU Tracker):** Assigns unique, persistent IDs to every dog, maintaining state memory across frames.
3. **Re-Identification (OSNet):** Extracts a 512-dimension vector to match tracked dogs against registered pet profiles using Cosine Similarity.
4. **Behavior Classification (MobileNetV2):** Performs real-time pose estimation (Sit, Stand, Lie) with Softmax confidence scoring.

#### 📊 Advanced Analytics Dashboard
The system features a rich, interactive dashboard with:
- **Global Filters:** Toggle between "Registered Pets", "Unidentified Dogs", or "All Dogs".
- **Dynamic Timeframes:** View activity for the Past Hour, Today, Past Week, or Monthly.
- **Visual Graphs:** Real-time Behavior Distribution (Pie Chart) and Activity Timeline (Stacked Bar Chart).
- **Auto-Capture:** Automatically captures and saves missing profile images for known pets and live snapshots for unidentified intruders.

#### 🚀 Installation & Hardware Setup
**Prerequisites:**
- Python 3.9+
- Linux/macOS/Windows (Tested on Ubuntu/Raspberry Pi OS)
- A working Web Camera (USB or Built-in) or a valid RTSP stream URL.

1. **Environment Setup:**
```bash
# Clone the repository
git clone git@github.com:akshaysatyam2/PupsN_Edge.git
cd PupsN_Edge

# Initialize a Virtual Environment to avoid system pollution
python3 -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate

# Install the strict dependencies
pip install -r requirements.txt
```

2. **Loading the AI Models (.onnx):**
Because .onnx files are extremely large binary weights, they are strictly ignored by Git. You must supply your own YOLO Nano and OSNet ONNX exports and place them in the `models/` directory:
- Place your YOLO ONNX export at: `models/yolo26nano.onnx`
- Place your OSNet ONNX export at: `models/osnet_x1_0.onnx`

#### 💻 Running the Application
Once dependencies and models are loaded, execute the main thread:
```bash
python app.py
```
**Accessing the Feed Locally & Over the Network:**
The Flask server binds strictly to `0.0.0.0:5000` via Eventlet/SocketIO.
- **On the Host Machine:** Open a browser to `http://localhost:5000`
- **Over the Local Network:** Open a browser to `http://<YOUR_LOCAL_IP>:5000`

#### 🛡️ Key Edge Optimizations Built-In
- **Explicit Memory De-allocation:** Python's native `gc.collect()` is triggered manually at the end of the streaming while-loop, preventing memory fragmentation over days of continuous operation.
- **RAM Map Caching:** Bypasses SQLite disk lookup latency by serializing BLOB weights back into numpy float32 arrays globally on application boot.
- **HTML5 Canvas:** Bypasses DOM memory leaks caused by rapid `<img>` src replacements by pushing Base64 JPEGs directly into a Javascript 2D Context render layer.
- **Hardware Queue Polling:** A secondary background thread isolates `cv2.VideoCapture.read()`, absorbing camera buffer buildup at native FPS while standardizing downstream AI checks to exactly 1.0 seconds (1 FPS) delta-time.

---

### ⚙️ Scalable Data Engineering Pipeline (Lakehouse Architecture)
**Tech Stack:** PySpark, dbt (data build tool), Terraform, AWS (S3, Glue, Redshift), Airflow, Docker

Designed and implemented a robust, end-to-end data engineering pipeline to handle large-scale data processing and analytics. This project demonstrates expertise in building modern data stacks using the Lakehouse architecture.

**Key Technical Features:**
- **Infrastructure as Code (IaC):** Leveraged **Terraform** to provision and manage AWS resources (S3 buckets, Redshift clusters, Glue crawlers), ensuring reproducible and scalable environments.
- **Data Orchestration:** Utilized **Apache Airflow** to schedule and monitor complex ETL workflows, ensuring data consistency and timely availability.
- **Big Data Processing:** Implemented high-performance data transformations using **PySpark**, handling multi-terabyte datasets with optimized partition strategies.
- **Data Modeling & Transformation:** Employed **dbt** for modular, version-controlled SQL transformations within the data warehouse, implementing rigorous testing and documentation.
- **Lakehouse Architecture:** Built a unified platform for both BI and AI by combining the low-cost storage of S3 with the high-performance querying of Redshift, managed by AWS Glue Catalog.

---

### 🧠 Building a Generative Diffusion Engine from Scratch
**Tech Stack:** Python, PyTorch, OpenCV, Generative AI, Deep Learning

**The Objective:**
While modern APIs make it easy to generate images with a single line of code, I wanted to deeply understand the fundamental mathematics powering state-of-the-art models like DALL-E and Sora. My goal was to build, debug, and train a Denoising Diffusion Probabilistic Model (DDPM) entirely from scratch using raw PyTorch.

**Technical Architecture & Implementation:**
- **The U-Net Bottleneck:** I built a custom YOLO-style U-Net equipped with skip connections to preserve spatial integrity. To allow the network to track its exact position in the 1000-step denoising process, I engineered and injected Sinusoidal Position Embeddings directly into the bottleneck.
- **The Math Schedule:** I implemented the forward diffusion process (adding noise) and the reverse diffusion process (removing noise) using a mathematically rigorous linear beta schedule.
- **Scaling to Production:** I scaled the model to train on the full 60,000-image MNIST dataset, adjusting tensor operations to handle 32x32 dimensional scaling and massively increasing batch sizes for gradient stability.

<div align="center">
  <img src="https://raw.githubusercontent.com/akshaysatyam2/diffusion-model/main/images/mnist/download.png" width="80" />
  <img src="https://raw.githubusercontent.com/akshaysatyam2/diffusion-model/main/images/mnist/download%20(1).png" width="80" />
  <img src="https://raw.githubusercontent.com/akshaysatyam2/diffusion-model/main/images/mnist/download%20(2).png" width="80" />
  <img src="https://raw.githubusercontent.com/akshaysatyam2/diffusion-model/main/images/mnist/download%20(3).png" width="80" />
  <img src="https://raw.githubusercontent.com/akshaysatyam2/diffusion-model/main/images/mnist/download%20(4).png" width="80" />
  <img src="https://raw.githubusercontent.com/akshaysatyam2/diffusion-model/main/images/mnist/download%20(5).png" width="80" />
  <img src="https://raw.githubusercontent.com/akshaysatyam2/diffusion-model/main/images/mnist/download%20(6).png" width="80" />
  <img src="https://raw.githubusercontent.com/akshaysatyam2/diffusion-model/main/images/mnist/download%20(7).png" width="80" />
  <img src="https://raw.githubusercontent.com/akshaysatyam2/diffusion-model/main/images/mnist/download%20(8).png" width="80" />
  <img src="https://raw.githubusercontent.com/akshaysatyam2/diffusion-model/main/images/mnist/download%20(9).png" width="80" />
</div>
<br/>

[**View Code**](https://github.com/akshaysatyam2/diffusion-model)

---

### 📷 YOLO Object Detection Suite
**Tech Stack:** YOLOv11, Object Detection, Computer Vision

This project focuses on object detection using YOLOv11 and other YOLO models. It automates the process of identifying objects in images, making it useful for various real-world applications like surveillance, quality control, and smart monitoring.

[**View Code**](https://github.com/akshaysatyam2/yolo-for-detection)

---

### 🐾 Multi-Class Object & Text Recognition Pipeline
**Tech Stack:** Object Detection, OCR, Computer Vision, Python

This project solves a very practical problem by detecting humans and animals in images and videos, classifying them correctly, and optionally running Optical Character Recognition (OCR) on the same media.

[**View Code**](https://github.com/akshaysatyam2/Man-Animal-and-Text)

---

### 🚁 Real-Time Drone Tracking System
**Tech Stack:** YOLO, SSD, Object Tracking, Computer Vision

An advanced system to detect and track drones effectively using YOLO and SSD (Single Shot MultiBox Detector) object detection models.

<div align="center">
  <img src="https://raw.githubusercontent.com/akshaysatyam2/TrackDrones/main/Task%203/val_batch0_pred.jpg" width="400" />
</div>
<br/>

[**View Code**](https://github.com/akshaysatyam2/TrackDrones)

---

### 🔳 Robust QR Code Detection
**Tech Stack:** OpenCV, QR Detection, Computer Vision, Python

A robust QR code detection and decoding pipeline using OpenCV, designed to handle challenging real-world conditions including noisy, rotated, or low-contrast images.

<div align="center">
  <img src="https://raw.githubusercontent.com/akshaysatyam2/QRReader/main/Outputs/Picture_1_result.jpg" width="200" />
  <img src="https://raw.githubusercontent.com/akshaysatyam2/QRReader/main/Outputs/Picture_2_result.jpg" width="200" />
</div>
<br/>

[**View Code**](https://github.com/akshaysatyam2/QRReader)

---

### 🔬 Drone Image Classification Research (CNN vs ResNet50)
**Tech Stack:** CNN, ResNet50, Deep Learning, Image Classification

This research provides a detailed comparative analysis of two deep learning approaches for drone image classification: standard CNNs and the ResNet50 architecture.

<div align="center">
  <img src="https://raw.githubusercontent.com/akshaysatyam2/CNN-vs-ResNet50-Classification/main/cnn_history.png" width="300" />
  <img src="https://raw.githubusercontent.com/akshaysatyam2/CNN-vs-ResNet50-Classification/main/resNet_history.png" width="300" />
</div>
<br/>

[**View Code**](https://github.com/akshaysatyam2/CNN-vs-ResNet50-Classification)

---

## Portfolio

Check out my live projects →  
[https://akshaysatyam2.github.io/akshaysatyam2/](https://akshaysatyam2.github.io/akshaysatyam2/)

---

## Let's Connect

- Email: akshaysatyam2003@gmail.com
- LinkedIn: [akshaysatyam2](https://www.linkedin.com/in/akshaysatyam2/)
- GitHub: [akshaysatyam2](https://github.com/akshaysatyam2)

> Always open to collaborations, research discussions, or just a quick chat!

<div align="center">
  <img src="https://media.giphy.com/media/LnQjpWaON8nhr21vNW/giphy.gif" width="60">
  <i>"Code. Deploy. Repeat."</i>
</div>
