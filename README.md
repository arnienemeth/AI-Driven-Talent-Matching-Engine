🧠 AI-Driven Talent Matching Engine

Stop keyword matching. Start semantic screening.

Traditional ATS systems fail because they treat CVs like keyword buckets.
This project introduces a semantic, human-centric recruitment engine that evaluates candidates the way a Senior Recruiter would — understanding skills, experience, leadership maturity, and potential.

Built with n8n + OpenAI + Google Workspace, this solution turns raw CVs into a ranked, decision-ready dashboard in seconds.

🚀 What This Project Does

This repository contains a fully automated AI-powered CV screening pipeline that:

Understands skills semantically, not literally

Applies weighted, recruiter-defined job requirements

Uses grace curves instead of rigid pass/fail logic

Produces clear hiring recommendations (STRONG_MATCH → NOT_RECOMMENDED)

Requires zero manual data entry

🎯 Why This Matters
❌ Traditional ATS

Keyword-based

Rigid filters

High false negatives

Black-box scoring

✅ This Engine

Context-aware semantic reasoning

Recruiter-friendly configuration (Google Sheets)

Transparent scoring logic

Designed to surface high-potential candidates

🧩 Core Features
✅ Semantic Intelligence

Understands that:

DAX ⇒ Power BI

PyTorch ⇒ Machine Learning

Lead Developer ⇒ Leadership & team management

✅ Dynamic Job Requirements

Job criteria live in Google Sheets

Update skills, weights, or priorities without touching the workflow

Supports multiple roles (e.g. Data Analyst, Architect, ML Engineer)

✅ Human-Centric Scoring

Weighted evaluation (hard skills, soft skills, experience)

Seniority bonuses

85% “grace rule” — perfection is not required

✅ Fully Automated Flow

From CV upload → ranked dashboard → optional recruiter notification

🏗️ Architecture Overview
Google Drive (CV Upload)
        ↓
n8n Workflow Orchestration
        ↓
Text Extraction (DOCX / Google Docs / PDF workaround)
        ↓
Semantic Analysis (OpenAI GPT-4o / GPT-4o-mini)
        ↓
Custom Scoring Logic (JavaScript)
        ↓
Google Sheets Results Dashboard

🧠 How the Engine Works (Step-by-Step)
1️⃣ Define the Ideal Candidate (Google Sheets)

Recruiters define:

Required skills (with importance weights)

Nice-to-have skills

Deal-breakers

Experience expectations

📄 Example role: Senior Data Analyst / Architect

LLM & Prompt Engineering → Must-have

Power BI, Excel, Power Query → Critical

Python → Intermediate

Tableau, University degree → Nice-to-have

2️⃣ CV Ingestion (Google Drive)

Upload a CV into a monitored folder

n8n automatically triggers the workflow

File metadata is captured

3️⃣ Text Extraction

Supports DOCX and Google Docs natively

PDF handling via Google Docs conversion (memory-safe)

Output: clean, normalized text

4️⃣ Semantic AI Evaluation (OpenAI)

The AI is instructed to:

Extract structured candidate data

Identify matched and missing skills

Infer experience and seniority

Assess leadership and overall fit

📤 Output is strict JSON for reliability.

5️⃣ Scoring Logic (Custom JavaScript)

The engine applies:

Weighted scoring based on job requirements

Deal-breaker enforcement

Experience multipliers

85% grace curve to avoid over-filtering

6️⃣ Results Dashboard (Google Sheets)

Each candidate receives:

Final score (0–100)

Recommendation flag

Strengths & concerns

Interview focus suggestions

This creates a live recruiter leaderboard.

📊 Recommendation Levels
Score Range	Recommendation
85–100	STRONG_MATCH
70–84	GOOD_MATCH
55–69	PARTIAL_MATCH
40–54	WEAK_MATCH
< 40	NOT_RECOMMENDED
🛠️ Tech Stack
Component	Purpose
n8n	Workflow orchestration
OpenAI (GPT-4o / 4o-mini)	Semantic analysis
Google Drive	CV ingestion
Google Sheets	Job requirements & results
JavaScript (Node.js)	Scoring & business logic
📁 Repository Structure
├── workflows/
│   ├── cv_screener_sequential.json
│   └── cv_screener_external_requirements.json
│
├── templates/
│   └── Job_Requirements_Template.xlsx
│
├── docs/
│   ├── architecture.png
│   └── scoring_logic.md
│
└── README.md

⚙️ Setup Guide (Quick Start)

Clone the repo

Import the workflow into n8n

Upload Job_Requirements_Template.xlsx to Google Sheets

Connect credentials:

Google Drive

Google Sheets

OpenAI

Upload a test CV (DOCX recommended)

Activate the workflow 🚀

⚠️ Known Limitations & Design Decisions

PDFs are memory-heavy → Google Docs conversion is recommended

AI output is validated and parsed defensively

Designed for screening support, not autonomous hiring decisions

🔮 Roadmap

Multi-language CV support

Bias & fairness diagnostics

Vector database for talent pooling

Hiring manager feedback loop

UI dashboard (Looker / Streamlit)

🧠 Philosophy

Recruitment shouldn’t be about filtering people out.
It should be about finding the right person, faster — and more fairly.

📬 Feedback & Contributions

This project is built #InPublic.
Ideas, issues, and pull requests are welcome.
