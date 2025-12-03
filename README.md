# 🧠 Intelligent Resume-Based Job Matching & Skill-Gap Recommendation System  
### _AI-Powered Resume Parsing • Job Matching • Skill-Gap Detection • Streamlit Dashboard_

---

## 🚀 Overview

This project is an end-to-end, AI-driven system that analyzes a resume, extracts skills, fetches live job listings, compares embeddings, detects missing skills, and recommends the best-matching jobs.

The system uses:

- **Streamlit** for the frontend UI  
- **AWS S3 + Lambda + MongoDB** for backend processing  
- **Sentence Transformers** for embeddings  
- **Adzuna API** for job fetching  
- **AI agent** for ranking, missing-skill detection & explanations  

---

## 🏗️ System Architecture

```mermaid
flowchart TD
    A[Streamlit Upload] --> B[S3 Bucket]
    B --> C[Lambda Trigger]
    C --> D[Resume Parsing - PyPDF]
    D --> E[Embedding Generation - MiniLM]
    E --> F[MongoDB: job_db]

    A2[Fetch Jobs Button] --> G[Adzuna API]
    G --> H[Job Embeddings]
    H --> I[MongoDB: jobs]

    A3[Compare Button] --> J[AI Matching Engine]
    J --> K[Top Job Matches + Skill Gaps]
