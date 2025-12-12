Intelligent Resume Screening System (SkillMatch)
Project Overview
SkillMatch is a functional prototype of an intelligent screening system designed to automate the initial resume assessment process for recruiters. It provides an objective relevance score by comparing candidate resumes against a Job Description (JD) using Natural Language Processing (NLP) and Machine Learning (ML) techniques.
Key Deliverable: This project focuses on Transparency, providing a visual, auditable breakdown of matching skills to overcome the "black-box" limitations of traditional Applicant Tracking Systems (ATS).
Objective	Status	Implementation Detail
Functional ML Code	✅ COMPLETE	Core matching logic implemented client-side in JavaScript (Jaccard Similarity proxy for TF-IDF).
Evaluation	✅ COMPLETE	Qualitative evaluation (Interpretability, Latency) and quantitative score distribution analysis.
Refinement	✅ COMPLETE	Integration of Gemini API for AI-powered Job Description refinement and keyword suggestion.
Transparency	✅ COMPLETE	Highlighted visualization of Matched (Green) and Missing (Red) keywords in the resume text.

📐 System Architecture and Algorithms
The system follows a three-tier logical architecture designed for rapid, real-time feedback.
1. NLP and ML Core (The Intelligence)
Role	Algorithm / Technique	Function in System
Tokenization & Preprocessing	Rule-Based Filtering & Normalization	Breaks raw text into clean, comparable tokens (keywords). Removes stop words (e.g., 'the', 'used') and converts text to lowercase.
Ranking Algorithm	Jaccard Similarity (Conceptual Proxy for Cosine/TF-IDF)	Calculates the quantitative match score based on the ratio of required JD keywords present in the resume.
Job-Candidate Matching	Keyword Set Intersection	Identifies which specific keywords from the JD intersect with the keywords in the resume for transparent visualization.
2. AI Service Integration (Refinement)
The project scope was expanded using the Gemini API to enhance input quality:
AI Service	Function	Impact
Gemini LLM (gemini-2.5-flash)	JD Refinement & Suggestion	Analyzes the recruiter's raw JD text and generates a clearer, structured JD, along with 5 suggested, high-value keywords to ensure the screening criteria is comprehensive.

🚀 How to Run the Application
Since the ML logic is implemented entirely in JavaScript, no backend server (Flask/Node.js) setup is required.
1.	Clone the Repository:
git clone [YOUR_REPOSITORY_URL]

2.	Locate the File: Open the project folder and find resume_screener.html.
3.	Run in Browser: Double-click the resume_screener.html file. It will open immediately in your default web browser (Chrome, Firefox, etc.).
4.	Test the Features:
○	The input fields are pre-filled with sample data.
○	Click "Screen and Rank Candidates (Batch Scan)" to see the score variation.
○	Click "View Analysis" on any row to see the transparent keyword highlighting.
⚠️ IMPORTANT NOTE: Activating the Gemini Feature
To enable the "✨ Refine JD with AI" feature, you must insert a valid Gemini API key into the source code:
1.	Open resume_screener.html.
2.	Find the line: const API_KEY = "";
3.	Replace the empty string with your actual key:
const API_KEY = "YOUR_ACTUAL_GEMINI_API_KEY_HERE"; 

📈 Evaluation Highlights
The core metric achieved is Interpretability. The system visually confirms the screening logic by highlighting:
●	Green: Matched keywords (Validation).
●	Red: Missing keywords (Actionable Feedback).
This feature directly addresses the market gap by providing a transparent, trust-based score.
