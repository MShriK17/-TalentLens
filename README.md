# 🚀 TalentLens – NLP-Powered Advanced Automated Applicant Tracking System for Resume Analysis and Candidate Ranking.

## 📌 Overview

**TalentLens** is a full-stack, NLP-powered Applicant Tracking System (ATS) designed to automate resume screening, candidate ranking, and recruiter workflows. The system leverages advanced Natural Language Processing (NLP) techniques to analyze resumes beyond simple keyword matching, providing accurate, explainable, and scalable hiring insights.

---

## 🎯 Key Features

* 📄 Resume Parsing (PDF & DOCX)
* 🧠 NLP-Based Skill Extraction (280+ skills + synonyms)
* 🔍 Named Entity Recognition (NER) using spaCy
* 📊 Multi-dimensional ATS Scoring System
* 🤖 Automatic Job Role Detection (Top-3 predictions)
* 📈 Interactive Analytics Dashboard
* 📑 PDF Report Generation
* 📧 Email Automation for Recruiters
* ⚡ Manual + Advanced Screening Modes

---

## 🏗️ System Architecture

### 🔹 3-Tier Architecture

1. **Frontend (Presentation Layer)**

   * React.js (Vite)
   * Handles UI, dashboards, file uploads

2. **Backend (Application Layer)**

   * FastAPI (Python)
   * Handles NLP processing, scoring, APIs

3. **Database (Data Layer)**

   * MongoDB
   * Stores resumes, analysis, job descriptions

---

## ⚙️ Tech Stack

### 🔹 Frontend

* React.js
* Tailwind CSS
* Axios
* Recharts / Chart.js

### 🔹 Backend

* FastAPI
* Python 3.11+
* Pydantic
* Uvicorn

### 🔹 NLP & Processing

* spaCy (NER)
* Regex
* TF-IDF concepts
* Cosine Similarity

### 🔹 Database

* MongoDB (Motor - async driver)

### 🔹 Deployment

* Backend: Render
* Frontend: Vercel

---



## 🔄 Workflow

1. User uploads resume (PDF/DOCX)
2. Backend extracts text
3. NLP pipeline processes data:

   * Contact extraction (regex)
   * Skill extraction (keywords + synonyms)
   * NER (spaCy)
   * Semantic similarity
4. ATS score is calculated
5. Role detection (Advanced mode)
6. Results stored in MongoDB
7. Dashboard visualizes insights
8. PDF report + email automation available

---

## 🧠 NLP Pipeline Details

* **Text Extraction** → PyPDF2 / python-docx
* **Tokenization & Cleaning**
* **Skill Extraction** → 280+ keyword dictionary
* **Synonym Resolution** → JS → JavaScript
* **NER** → spaCy (ORG, PRODUCT)
* **Semantic Matching** → Cosine Similarity

---

## 📊 ATS Scoring Algorithm

| Parameter   | Weight |
| ----------- | ------ |
| Skills      | 45%    |
| Experience  | 25%    |
| Education   | 10%    |
| Title Match | 10%    |
| Keywords    | 10%    |

### Formula:

```
ATS Score = (Skill × 0.45) + (Experience × 0.25) + (Education × 0.10) + (Title × 0.10) + (Keywords × 0.10)
```

---

## 🚀 Setup & Installation

### 🔹 Backend Setup

```bash
cd backend
pip install -r requirements.txt
uvicorn server:app --reload
```

### 🔹 Frontend Setup

```bash
cd frontend
npm install
npm start
```

---

## 🌐 Deployment Guide

### 🔹 Backend (Render)

1. Push backend code to GitHub
2. Create new Web Service on Render
3. Set:

   * Build Command: `pip install -r requirements.txt`
   * Start Command: `uvicorn server:app --host 0.0.0.0 --port $PORT`
4. Add `MONGO_URL`, `DB_NAME`, and `CORS_ORIGINS` in Render. Add the `MAIL_*` variables if email delivery is required.
5. Verify `/health` returns `{"status":"ok","database":"ok"}`.

---

### 🔹 Frontend (Vercel)

1. Import the repository in Vercel.
2. Set the root directory to `frontend`.
3. Vercel will use `npm run build` and the included SPA rewrite.
4. Add `REACT_APP_BACKEND_URL` with the deployed Render backend URL, without a trailing slash.
5. Redeploy after setting the variable.

---

## 🌏 Live Application : https://talent-lens-psi.vercel.app/

## 🔐 Environment Variables

Backend variables are documented in `backend/.env.example`; frontend variables are documented in `frontend/.env.example`. Never commit real credentials or `.env` files.

---

## 📈 Future Enhancements

* OCR for scanned resumes
* Integration with job portals
* AI-based resume improvement suggestions
* Real-time collaboration for recruiters

---

## 👨‍💻 Contributors

* Prasen Nimje
* Mahesh Khumkar
* Nishant Chaudhari

---

## 📬 Contact

📧 [prasennimje100@gmail.com](mailto:prasennimje100@gmail.com)
🔗 LinkedIn: https://www.linkedin.com/in/prasen-nimje

---

## ⭐ If you like this project, give it a star!

