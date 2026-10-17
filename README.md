# TalentLens AI — NLP-Powered Applicant Tracking System

**TalentLens AI** is a full-stack Applicant Tracking System (ATS) designed to streamline resume screening, skill extraction, candidate ranking, and recruitment workflows using Natural Language Processing (NLP).

The platform helps recruiters analyze resumes, compare candidate profiles against job requirements, and generate structured screening insights through an interactive web interface.

## 🚀 Live Demo

- **Frontend:** https://talent-lens-opal.vercel.app/
- **Backend API:** https://talentlens-api-oqw0.onrender.com
- **API Documentation:** https://talentlens-api-oqw0.onrender.com/docs

> Note: The backend may take some time to respond after a period of inactivity because it runs on Render's free instance.

## ✨ Key Features

- **Resume Parsing:** Extract text and information from PDF and DOCX resumes.
- **Skill Extraction:** Identify technical skills using a skill dictionary, keywords, and synonyms.
- **Named Entity Recognition:** Use spaCy to identify relevant entities in resume text.
- **ATS Scoring:** Evaluate resumes using multiple job-relevant criteria.
- **Automatic Role Detection:** Predict suitable job roles and display top role matches.
- **Candidate Ranking:** Compare resumes against job descriptions and rank candidates.
- **Advanced Screening:** Support automated screening workflows alongside manual screening.
- **Analytics Dashboard:** Present screening results and candidate insights.
- **PDF Reports:** Generate downloadable resume analysis reports.
- **Email Automation:** Support recruiter email workflows when SMTP is configured.

## 🏗️ System Architecture

TalentLens follows a three-tier architecture.

| Layer | Technology | Responsibility |
|---|---|---|
| Presentation | React.js, Tailwind CSS, Axios | User interface, uploads, dashboards |
| Application | FastAPI, Python, spaCy | Resume processing, scoring, API endpoints |
| Data | MongoDB, Motor | Resume records, analysis results, application data |
| Deployment | Vercel, Render | Frontend hosting and backend hosting |

## 🧰 Tech Stack

**Frontend**
- React.js
- Tailwind CSS
- Axios
- JavaScript

**Backend**
- Python
- FastAPI
- Uvicorn
- Pydantic

**NLP and Processing**
- spaCy
- Regular expressions
- PDF and DOCX text extraction
- Keyword and synonym matching
- TF-IDF and cosine similarity concepts

**Database and Deployment**
- MongoDB
- Motor asynchronous database driver
- Git and GitHub
- Render
- Vercel

## 🔄 How It Works

1. The user uploads a resume in PDF or DOCX format.
2. The backend extracts text and relevant information.
3. The NLP pipeline processes the text and identifies skills and entities.
4. The system evaluates the candidate using the implemented scoring criteria.
5. Advanced screening can identify suitable job roles and candidate matches.
6. Analysis results are stored in MongoDB.
7. The frontend displays the results and dashboard insights.
8. Users can generate reports and use email functionality when configured.

## 📊 ATS Scoring Model

The project uses a weighted scoring model to evaluate candidate suitability.

| Criterion | Weight |
|---|---:|
| Skills | 45% |
| Experience | 25% |
| Education | 10% |
| Job Title Match | 10% |
| Keywords | 10% |
| **Total** | **100%** |

The scoring formula is:

`ATS Score = (Skills × 0.45) + (Experience × 0.25) + (Education × 0.10) + (Title Match × 0.10) + (Keywords × 0.10)`

Scores are screening indicators, not guarantees of candidate suitability. Actual hiring decisions should include human review.

## ⚙️ Local Installation

### Prerequisites

- Python 3.11 recommended
- Node.js and npm
- MongoDB Atlas account or a compatible MongoDB instance
- Git

### 1. Clone the repository

```bash
git clone https://github.com/MShriK17/-TalentLens.git
cd -TalentLens
```

### 2. Set up the backend

```bash
python -m venv .venv
```

Activate the virtual environment.

**Windows PowerShell:**

```powershell
.\.venv\Scripts\Activate.ps1
```

Install the dependencies:

```bash
pip install -r backend/requirements.txt
```

Configure the backend environment variables in `backend/.env` using the example file provided in the repository.

At minimum, configure:

```env
MONGO_URL=your_mongodb_connection_uri
DB_NAME=Resume_Main
```

Start the backend from the repository root:

```bash
python -m uvicorn server:app --app-dir backend --reload
```

Backend address: `http://localhost:8000`

API documentation: `http://localhost:8000/docs`

### 3. Set up the frontend

Open a second terminal:

```bash
cd frontend
npm install
```

Create or configure the frontend `.env` file:

```env
REACT_APP_BACKEND_URL=http://localhost:8000
```

Start the frontend:

```bash
npm start
```

Use the local address displayed by the frontend development server.

## 🌐 Deployment

### Backend — Render

1. Connect the GitHub repository to Render.
2. Create a Python web service.
3. Set the root directory to `backend`.
4. Configure the build command:

   ```bash
   pip install -r requirements.txt
   ```

5. Configure the start command:

   ```bash
   uvicorn server:app --host 0.0.0.0 --port $PORT
   ```

6. Set `MONGO_URL` and `DB_NAME` in the Render environment settings.
7. Configure `CORS_ORIGINS` with the deployed frontend origin.
8. Configure the `MAIL_*` variables if email delivery is required.
9. Verify the `/health` endpoint after deployment.

### Frontend — Vercel

1. Import the repository into Vercel.
2. Set the root directory to `frontend`.
3. Use the detected Create React App framework configuration.
4. Set the environment variable:

   ```env
   REACT_APP_BACKEND_URL=https://talentlens-api-oqw0.onrender.com
   ```

5. Deploy the project and test frontend-to-backend communication.

Redeploy after changing environment variables.

## 🔐 Security

- Never commit `.env` files, passwords, API keys, or database credentials.
- Use environment variables for deployment secrets.
- Restrict database access appropriately.
- Configure CORS for trusted frontend origins.
- Review candidate information responsibly and protect personal data.

## 🔮 Future Enhancements

- OCR support for scanned resumes.
- Integration with job portals.
- AI-powered resume improvement suggestions.
- Advanced semantic matching and explainability.
- Recruiter collaboration features.
- Improved evaluation and model benchmarking.

## 👨‍💻 Author and Contributors

**Mahesh Khumkar** — AI & Data Science Engineering graduate and developer working on TalentLens.

This project originated as a collaborative project. Add the other contributors and describe their contributions where appropriate.

## 📬 Contact

- **GitHub:** https://github.com/MShriK17
- **LinkedIn:** Add your LinkedIn profile URL.

---

If you find this project useful, consider giving the repository a ⭐ on GitHub.
