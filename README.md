# 📄 ATS Resume Checker

A Streamlit app that scores a resume for Applicant Tracking System (ATS) compatibility and
suggests specific improvements, powered by Google's Gemini Flash model.

## Features
- Upload a resume as **PDF, DOCX or TXT**
- Optional **job description** field for tailored keyword matching
- ATS score (0-100) with a breakdown: formatting, keywords, experience, education & skills, readability
- Strengths, matched/missing keywords, and prioritized improvements

## Run locally
```bash
git clone <your-repo-url>
cd <your-repo>
python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

Get a free API key at https://aistudio.google.com/apikey, then provide it in one of these ways:

1. Paste it into the sidebar when the app runs, or
2. Set an environment variable: `export GEMINI_API_KEY="your-key"`, or
3. Create `.streamlit/secrets.toml` containing `GEMINI_API_KEY = "your-key"`

```bash
streamlit run app.py
```

## Deploy on Streamlit Community Cloud
1. Push this repo to GitHub (do **not** commit your API key).
2. Go to https://share.streamlit.io and sign in with GitHub.
3. Click **Create app**, choose your repo, branch `main`, and main file `app.py`.
4. Open **Advanced settings → Secrets** and add: `GEMINI_API_KEY = "your-key"`
5. Click **Deploy**.

## Notes
- Model used: `gemini-2.5-flash` (change `MODEL_NAME` in `app.py` to switch).
- Scanned/image-only PDFs contain no extractable text; use a text-based PDF.
- Scores are AI estimates, not the output of any real ATS. Treat them as guidance.
- Resume text is sent to the Gemini API for analysis. Avoid uploading sensitive documents you don't want processed.

## Files
- `app.py` - the Streamlit application
- `requirements.txt` - Python dependencies
- `README.md` - this file
