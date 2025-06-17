# SmartChest AI: Detect, Describe & Visualize Diseases in X-Rays & CT Scans

SmartChest AI is an intelligent, web-based diagnostic tool designed to automate the analysis of chest radiology images—including both 2D X-rays and 3D CT scans. It empowers medical professionals and researchers with real-time disease detection, explainable AI (XAI), and natural language diagnostic reports.

This system bridges cutting-edge AI with real-world radiology needs, making high-quality diagnostics accessible even in resource-limited environments.

### SmartChest AI User Interface

![SmartChest AI UI](https://github.com/user-attachments/assets/d773f26b-16ac-4ab4-a251-e7a5c15a3762)


---

## Features

* Chest X-ray Disease Detection using DenseNet-121
  Trained on a large NIH dataset to detect 14 common thoracic diseases such as Pneumonia, Fibrosis, Cardiomegaly, etc., with high AUC scores.

* Grad-CAM Heatmaps for Visual Explanation
  Generates heatmaps overlayed on X-rays to highlight the most influential areas contributing to predictions.

* 3D CT Scan Analysis using Vision Transformers (CT-ViT)
  Uses a 3D Vision Transformer architecture to analyze volumetric chest CT scans effectively, extracting contextual spatial information.

* Structured Report Generation using Mistral-7B
  Automatically generates radiologist-style diagnostic reports from CT scans using a quantized Mistral-7B LLM enhanced with LoRA fine-tuning.

* Modern Web Interface (React + Flask)
  Built with a stylish, animated frontend and a robust Flask backend. Smooth image upload, visual results, and progress animations enhance UX.

* Multi-Disease Prediction with Confidence Scores
  Detects multiple diseases simultaneously and displays each with a confidence score for interpretability.

* Downloadable Reports & Visuals
  Option to download PDF reports, heatmap overlays, and predictions for offline reference or record-keeping.


---

## Tech Stack

| Layer             | Technologies                                                              |
| ----------------- | ------------------------------------------------------------------------- |
| **Frontend**      | React.js, Material-UI, CSS, Axios, Framer Motion                          |
| **Backend**       | Flask, Python, TensorFlow, PyTorch, OpenCV                                |
| **Models**        | DenseNet-121 (X-ray), CT-ViT (3D ViT for CT), Mistral-7B (LLM)            |
| **NLP**           | HuggingFace Transformers, LoRA adapter, 4-bit quantization (bitsandbytes) |
| **Visualization** | Grad-CAM, ROC curves, Matplotlib                                          |
| **Deployment**    | Localhost (Flask + React) with future support for Heroku, AWS, etc.       |

---

##  Real-World Motivation

Manual diagnosis of chest radiology is time-consuming and often inconsistent across practitioners. SmartChest AI addresses:
* Shortage of radiologists in rural or under-resourced settings.
* Variability in manual interpretations.
* Need for fast and explainable decision-making support in hospitals.

This project was built as part of a B.Tech major project at Mahatma Gandhi Institute of Technology (MGIT), Hyderabad (2024-2025)

---

##  Demo Screenshots

### Upload Chest X-ray Image or CT scan Image and click Start Analyze Button

![Upload](https://github.com/user-attachments/assets/9a5dfff8-5bc3-44ac-9f96-50ab56c6f14a)
### Start’s Analyzing the Uploaded Chest X-ray or CT scan Image

![Alalyze](https://github.com/user-attachments/assets/00b2c8bb-6208-4672-8e3c-b2a1a4ffbe90)
### Diagnosis Results of Uploaded Chest X-ray Image

![X-ray result](https://github.com/user-attachments/assets/db371a61-cfbe-4b10-a2aa-77f387440e3c)
### Disease Findings of Chest X-ray Image through Grad-cam

![Grad-Cam](https://github.com/user-attachments/assets/ae9559b2-56c2-4258-a90d-b01b4889fd17)
### Detail Description about the Findings and Impression of Uploaded CT Scan

![CT result](https://github.com/user-attachments/assets/1fc0661a-a423-41d3-997c-8eaa2447045f)

---

## How It Works

### X-Ray Pipeline

* Upload chest X-ray (JPG/PNG).
* Image is resized and normalized.
* DenseNet-121 predicts 14 diseases from NIH ChestX-ray14.
* Grad-CAM heatmaps highlight regions influencing predictions.
* Visual + textual output shown in results UI.

### CT Pipeline

* Upload CT Scan in NIfTI format.
* Preprocessing includes HU clipping & isotropic resampling.
* CT-ViT extracts spatio-temporal embeddings.
* A projection head aligns the vector with the Mistral-7B input space.
* An LLM generates a radiology-style Findings & Impression report.

---

## Future Scope

* Integrate cloud deployment (Render/Heroku/AWS EC2)
* Add DICOM viewer & 3D CT slice navigator
* Improve CT-ViT training using larger curated datasets
* Add patient data integration for real-world deployments
* Add user authentication and report saving features

---

## Authors

* **Kandula Sai Grahith** – 21261A0519
* **Bonam Naga Suresh** – 21261A0508

Project under guidance of **Dr. C.R.K Reddy** and **Dr. Meera Alphy**, Department of CSE, MGIT, Hyderabad.


