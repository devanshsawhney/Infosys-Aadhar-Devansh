# Infosys Aadhaar Fraud Detection System

This repository contains an end-to-end Aadhaar Fraud Detection System built using **FastAPI**, **React (Vite)**, **EasyOCR / Tesseract OCR**, **OpenCV**, **Machine Learning**, and **QR Code Decoding**.

Live Deployment Links:

* **Frontend:** [https://e71089df.infosys-aadhar-devansh.pages.dev/dashboard](https://e71089df.infosys-aadhar-devansh.pages.dev/dashboard)
* **Backend (HuggingFace API):**

  * [https://huggingface.co/spaces/VinuthnaPesara/UID_Aadhaar](https://huggingface.co/spaces/VinuthnaPesara/UID_Aadhaar)
  * [https://vinuthnapesara-uid-aadhaar.hf.space/](https://vinuthnapesara-uid-aadhaar.hf.space/)

---

## 🚀 Project Overview

This project detects fraudulent Aadhaar cards using AI-based OCR, QR code validation, document feature extraction, and image analysis. It integrates a FastAPI backend with a React frontend for a seamless user experience.

---

## 🔧 Tech Stack

### **Backend (FastAPI)**

* Python
* FastAPI
* Uvicorn
* OpenCV
* EasyOCR
* Pyzbar for QR decoding
* ML model support (ResNet-based Aadhaar real/fake classifier)

### **Frontend (React - Vite)**

* React 19
* Axios
* Vite build & deployment via Cloudflare Pages

---

## 📂 Project Structure

```
Infosys-Aadhar-Devansh/
│── src/
│   ├── api.py              # FastAPI main file
│   ├── qr_utils.py         # QR code detection & parsing
│   ├── ocr_utils.py        # EasyOCR text extraction
│   ├── fraud_model.py      # ML model handling
│   └── ...
│
│── aadhaar-ui/             # React Frontend
│   ├── src/
│   ├── dist/               # Production build folder
│   └── package.json
│
│── artifacts/              # Model weights (ignored if missing)
│── README.md
└── ...
```

---

## 🧠 AI Features

### **1. OCR Text Extraction (EasyOCR + Tesseract)**

* Automatically extracts:

  * Name
  * DOB
  * Gender
  * Aadhaar number
* Performs formatting & validation.

### **2. QR Code Authenticity Check**

* Extracts data from the Aadhaar QR.
* Compares:

  * OCR vs QR extracted values.
  * Photo hash integrity.
* Validates Verhoeff checksum.

### **3. Image Fraud Detection Model**

* CNN-based binary classifier (**real vs fake Aadhaar**).
* Detects:

  * Blur patterns
  * Edge inconsistencies
  * Tampering marks

---

## 🖥️ Dashboard Features

* Upload Aadhaar image
* OCR results displayed
* QR code verification
* AI fraud probability score
* Final decision shown clearly

Live dashboard: **[https://e71089df.infosys-aadhar-devansh.pages.dev/dashboard](https://e71089df.infosys-aadhar-devansh.pages.dev/dashboard)**

---

## 🛠️ How to Run Locally

### Backend

```
cd src
pip install -r requirements.txt
uvicorn api:app --reload
```

### Frontend

```
cd aadhaar-ui
npm install
npm run dev
```

Build for deployment:

```
npm run build
```

---

## 🌐 Deployment

### **Backend:** Cloudflare Workers (static hosting or API gateway)

### **Frontend:** Cloudflare Pages using Vite build

The `dist/` folder from React is deployed to Cloudflare Pages.

---

## 📌 Author

**Devansh Sawhney**

* Data Science & Artificial Intelligence
* University of Delhi

---

## 📄 License

This project is created as part of the Infosys–Aadhaar Verification Module. Suitable for research and learning purposes.
