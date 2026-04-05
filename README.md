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

**Computer Vision Engineer | ML Researcher**  
Real-time CV on edge devices • Deep Learning • Generative AI • MLOps  

Passionate about turning research into production-grade solutions using **Computer Vision**, **NLP**, and **Deep Learning**.

---

### GitHub Activity & Stats

<div align="center">

<!-- Reliable GitHub Stats -->
<img src="https://github-readme-stats.vercel.app/api?username=akshaysatyam2&show_icons=true&theme=tokyonight&hide_border=true" alt="GitHub Stats" width="800"/>

<br/><br/>

<!-- Streak – the only host that never dies -->
<img src="https://streak-stats.demolab.com?user=akshaysatyam2&theme=tokyonight&hide_border=true&background=0d1117&stroke=7c3aed&ring=7c3aed&fire=ff6b6b&currStreakLabel=7c3aed&currStreakNum=7c3aed&sideNums=7c3aed&dates=8b9494"/>

<br/>

<!-- Trophy case (instant load, pure flex) -->
<img src="https://github-profile-trophy.vercel.app/?username=akshaysatyam2&theme=tokyonight&no-frame=true&margin-w=15&margin-h=15&column=7"/>

<br/>

<!-- Profile views -->
<img src="https://komarev.com/ghpvc/?username=akshaysatyam2&label=Profile+Views&color=7c3aed&style=flat-square"/>

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
