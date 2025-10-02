<p align="center">
  <!-- Core -->
  <a href="https://www.python.org/"><img src="https://img.shields.io/badge/Python-3.10+-blue.svg" alt="Python"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-green.svg" alt="License: MIT"></a>
  <img src="https://img.shields.io/github/last-commit/thomas-sabu-cs/career-skill-recommender.svg" alt="Last Commit">
  <a href="https://github.com/thomas-sabu-cs/career-skill-recommender/issues"><img src="https://img.shields.io/github/issues/thomas-sabu-cs/career-skill-recommender.svg" alt="Issues"></a>
  <a href="https://github.com/thomas-sabu-cs/career-skill-recommender/stargazers"><img src="https://img.shields.io/github/stars/thomas-sabu-cs/career-skill-recommender.svg?style=social" alt="Stars"></a>
  <a href="https://github.com/thomas-sabu-cs/career-skill-recommender/network/members"><img src="https://img.shields.io/github/forks/thomas-sabu-cs/career-skill-recommender.svg?style=social" alt="Forks"></a>
  <img src="https://img.shields.io/github/repo-size/thomas-sabu-cs/career-skill-recommender.svg" alt="Repo size">

  <!-- Contribution -->
  <a href="https://github.com/thomas-sabu-cs/career-skill-recommender/pulls"><img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg" alt="PRs Welcome"></a>

  <!-- Tech highlights -->
  <img src="https://img.shields.io/badge/Jupyter-Notebook-orange.svg" alt="Jupyter">
  <img src="https://img.shields.io/badge/scikit--learn-TF--IDF%20%7C%20Cosine%20Similarity-ff69b4.svg" alt="scikit-learn">

  <!-- Colab launcher -->
  <a href="https://colab.research.google.com/github/thomas-sabu-cs/career-skill-recommender/blob/main/notebooks/01_mvp_recommender.ipynb">
    <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab">
  </a>
</p>

# Career-Skill Recommender System

## 🚀 Project Overview
The Career-Skill Recommender System is an AI-powered tool that helps job seekers discover career paths and identify skill gaps.

Given a list of user skills, the system:
- 🔍 Recommends relevant job roles by comparing user skills against real job postings
- 📉 Finds missing skills for a desired role (skill gap analysis)
- 🎯 Provides a foundation for personalized career guidance tools

This project showcases end-to-end ML engineering: data → modeling → recommendations → (future) API + deployment.

## 📊 Dataset
- Source: Kaggle (LinkedIn job postings dataset)
- Size: 124k+ job postings with titles, descriptions, and inferred skills
- Columns used: `title`, `description`, `skills_desc`, plus metadata (location, salary, etc.)

Note: Due to licensing, raw data is not committed. Place `job_postings.csv` in the local `data/` folder to run.

## 🧠 Techniques
- NLP preprocessing: regex keyword extraction of skills from job text
- Representations: TF‑IDF skill embeddings per role
- Similarity search: cosine similarity between user skills and role profiles
- Skill gap analysis: missing skills = role’s skills − user’s skills

Planned upgrades: embeddings (SBERT/Word2Vec) and OpenSkills/O*NET taxonomy for robust skill parsing.

## ⚙️ Tech Stack
- Python 3.x
- pandas, scikit-learn, regex, numpy
- Jupyter Notebooks for experimentation
- Future: FastAPI service + simple frontend

## 📂 Repo Structure

career-skill-recommender/  
├─ data/ # Local dataset (not tracked in git)  
│ └─ job_postings.csv  
├─ notebooks/ # Jupyter notebooks (MVP logic)  
│ └─ 01_mvp_recommender.ipynb  
├─ src/ # Source code (future: pipeline/API)  
├─ requirements.txt # Dependencies  
├─ README.md # Project overview (this file)  
├─ LICENSE # License  
└─ .gitignore # Ignore data & artifacts  
  
## ▶️ How to Run
1) Clone the repo
```bash

git clone https://github.com/<your-username>/career-skill-recommender.git
```
AND
```bash
cd career-skill-recommender
```
2) Install dependencies in CMD:
```bash
pip install -r requirements.txt
```
3) Prepare data
  - Download the Kaggle CSV and place job_postings.csv in data/

4) Launch the MVP notebook
jupyter notebook notebooks/01_mvp_recommender.ipynb
(If needed, update DATA_DIR in the notebook to point to your local data/ path)

## 📈 Example Output
Input: user = ["python", "sql", "pandas"]  

Output:  
--- Recommended Roles ---  
[('Python Developer with AI/ML Skills', 0.724),  
 ('Data Scientist - AI Investment', 0.690),  
 ('Machine Learning Engineer', 0.662),  
 ...]  

--- Missing Skills (Data Scientist variants) ---  
['machine learning', 'deep learning', 'aws', 'docker', 'tensorflow']  

## 🔮 Roadmap
- ✅ MVP recommender with TF‑IDF + regex
- 🚧 Upgrade to embeddings (SBERT / Word2Vec)
- 🚧 Serve as REST API (FastAPI)
- 🚧 Add web UI for interactive use
- 🚧 Deploy to cloud (Heroku/AWS or Hugging Face Spaces)

📜 License
MIT License © 2025
