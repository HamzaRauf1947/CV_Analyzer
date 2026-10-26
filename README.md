# AI-Powered CV / Resume Analyzer Using NLP

A university NLP project prototype based on the supplied project proposal. It accepts PDF/DOCX resumes, extracts text, checks common sections, returns LanguageTool grammar suggestions (if LanguageTool starts successfully), flags a small list of vague phrases, and optionally compares a resume with a job description using TF-IDF and cosine similarity.

## Requirements
- Windows 10/11, macOS, or Linux
- Python 3.10–3.12 recommended
- Internet connection for installing packages and for LanguageTool's initial setup (depending on the installation/environment)

## Setup on Windows
1. Install Python from https://www.python.org/downloads/ and enable **Add Python to PATH**.
2. Extract this ZIP to a folder, for example `AI_CV_Resume_Analyzer_NLP`.
3. Open that folder in Visual Studio Code.
4. Open Terminal → New Terminal.
5. Create and activate a virtual environment:

   ```powershell
   py -m venv .venv
   .\.venv\Scripts\Activate.ps1
   ```

   If PowerShell blocks activation, use Command Prompt and run:
   ```bat
   .venv\Scripts\activate.bat
   ```

6. Install libraries:
   ```powershell
   python -m pip install --upgrade pip
   pip install -r requirements.txt
   ```
7. `requirements.txt` also installs the English spaCy model. If that step fails, run:
   ```powershell
   python -m spacy download en_core_web_sm
   ```
8. Start the app:
   ```powershell
   streamlit run app.py
   ```
9. A browser tab should open. Upload a text-based PDF or DOCX and click **Analyze Resume**.

## Run it on the web
Use the free Streamlit Community Cloud so the app has its own address and does not need your laptop to stay on.

1. Create a free GitHub account at https://github.com if you do not have one.
2. Create a new public repository and upload this folder. Do not upload `.venv`.
3. Sign in at https://share.streamlit.io with that GitHub account.
4. Choose **Create app**, select the repository, set the main file to `app.py`, then deploy.
5. Open the `*.streamlit.app` address from any phone or computer.

The first visit can take several minutes. The host installs Python libraries, Java, and LanguageTool. After the app has been idle, the free host sleeps and wakes again when someone opens the link. Do not upload real personal resumes to a public address.

## Test plan
Try at least:
- A DOCX resume with Summary, Skills, Experience, Education, Projects.
- A PDF resume with some sections missing.
- A resume containing phrases such as “was responsible for” and “helped with”.
- The same resume with and without a target job description.
- A scanned/image-only PDF (the app should report that no readable text was extracted; OCR is not included).

Record the expected and actual outcomes in your project report. Do not claim a test passed unless you run it.

## Important limitations
- The overall score is a transparent, hand-designed heuristic, not a scientifically validated ATS score.
- Section detection relies on common heading keywords.
- The basic missing-keyword list is a simple word overlap heuristic; it can flag irrelevant words.
- Readability is represented by average sentence length; passive-voice detection is not implemented reliably.
- Grammar results depend on LanguageTool availability and its rules.
- The app does not save analysis history to a database in this starter version.
- The app is a prototype, not a hiring decision tool. Review all suggestions manually.

## Main NLP concepts for your presentation
- Text extraction and cleaning
- Tokenization and sentence segmentation (spaCy model is loaded when installed)
- Named Entity Recognition is part of the proposal and can be added as an extension
- Grammar checking with LanguageTool
- TF-IDF vectorization
- Cosine similarity
- Rule-based section and weak-phrase detection

## Possible future improvements
- Display spaCy entities and part-of-speech tags.
- Add robust passive-voice detection.
- Improve skill extraction with a curated skills taxonomy.
- Export a formatted PDF report.
- Add tests and an optional database for history.
- Implement the original Next.js + FastAPI architecture if required by the instructor.
