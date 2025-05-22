# CV–Job Matching System

This project implements a full pipeline to match candidate CVs with job vacancies using NLP techniques. It extracts key information, parses job requirements, vectorizes features, computes scores, and ranks candidates accordingly.

---

## 📁 Project Structure

```bash
project-root/
├── data/
│   ├── cvs/               # Raw CV files (PDF/DOCX)
│   └── job/               # Raw vacancy post (PDF/DOCX or TXT)
├── src/
│   ├── text_extraction.py # Batch-convert PDFs/DOCX → TXT
│   ├── entity_extraction.py
│   │   └── extract_education()
│   │   └── extract_experience()
│   │   └── extract_skills()
│   ├── vacancy_parsing.py # Parse job requirements into schema
│   ├── vectorize.py       # Build feature vectors for CVs & vacancy
│   ├── scoring.py         # Compute matching scores & rankings
│   └── utils.py           # Shared helpers (e.g. file I/O, date parsers)
├── outputs/
│   ├── text/              # Cleaned .txt versions of all docs
│   ├── entities.json      # Parsed CV & vacancy fields
│   ├── ranking.csv        # Final ranked shortlist
│   └── plots/             # Score bar chart, etc.
├── requirements.txt       
├── README.md              # Project overview & “one-command” run
├── main.py                # Shell script to run end-to-end pipeline
└── dashboard.py           # Streamlit app for interactive viewing

---

## ⚙️ Configuration & Running the Dashboard

1. **Set your OpenAI API key**  
    Create a `.env` file in the project root with the following content:
    ```env
    OPENAI_API_KEY=your_openai_api_key_here
    ```
    Replace `your_openai_api_key_here` with your actual OpenAI API key.

2. **Launch the Streamlit dashboard**  
    Run the following command from the project root:
    ```bash
    streamlit run dashboard.py
    ```
    This will start the interactive dashboard in your browser.