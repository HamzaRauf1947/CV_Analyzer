# AI-Powered CV / Resume Analyzer Using NLP
## Topic of Current Interest — NLP Project Report

**Student name(s):** [Add names]  
**Department / University:** [Add details]  
**Instructor:** [Add instructor name]  
**Submission date:** [Add date]

## 1. Abstract
This project presents a prototype web application that uses Natural Language Processing techniques to analyze CV/resume text. It extracts text from PDF and DOCX documents, checks for common resume sections, reports grammar suggestions when the grammar engine is available, flags selected vague phrases, and compares resume text with a target job description using TF-IDF and cosine similarity. The system provides feedback to help users review and improve their resumes.

## 2. Problem Statement
Job applicants may overlook grammar problems, unclear phrasing, missing resume sections, and terms relevant to a particular job. Manually checking every resume can be time-consuming. This project explores how NLP techniques can automate basic checks and provide structured feedback.

## 3. Objectives
- Extract text from PDF and DOCX resumes.
- Check for common sections such as Summary, Skills, Experience, Education, and Projects.
- Return grammar and spelling suggestions using LanguageTool when available.
- Flag a small set of vague phrases and suggest reviewing them.
- Compare a resume against a job description with TF-IDF and cosine similarity.
- Present a simple guidance score and downloadable summary.

## 4. Methodology
1. **Input:** User uploads a PDF/DOCX and optionally supplies a job description.
2. **Text extraction:** pdfplumber or python-docx extracts text.
3. **Section detection:** rule-based patterns check for common headings.
4. **Grammar checking:** LanguageTool returns possible issues and corrections.
5. **Phrase analysis:** predefined rules identify selected vague expressions.
6. **Text similarity:** TF-IDF vectors and cosine similarity estimate textual overlap.
7. **Output:** the application displays a structured report and offers a text download.

## 5. Technology Stack
Python, Streamlit, spaCy, LanguageTool, pdfplumber, python-docx, scikit-learn.

## 6. Testing and Validation
Fill this table only after running each test. Include screenshots where possible.

| Test case | Input | Expected result | Actual result | Status |
|---|---|---|---|---|
| T1: DOCX extraction | Text-based DOCX resume | Resume text appears in preview | [Record result] | [Pass/Fail] |
| T2: PDF extraction | Text-based PDF resume | Resume text appears in preview | [Record result] | [Pass/Fail] |
| T3: Empty/scanned PDF | PDF with no selectable text | Clear no-readable-text warning | [Record result] | [Pass/Fail] |
| T4: Section check | Resume with known headings | Corresponding sections detected | [Record result] | [Pass/Fail] |
| T5: Grammar check | Text containing deliberate errors | Grammar suggestions shown if engine available | [Record result] | [Pass/Fail/Unavailable] |
| T6: Job matching | Resume and job description | Similarity and keyword differences shown | [Record result] | [Pass/Fail] |
| T7: Report download | Completed analysis | Summary TXT downloads | [Record result] | [Pass/Fail] |

## 7. Results
[Insert real screenshots and summarize observations after running the tests. Do not invent results.]

## 8. Limitations
The score is a hand-designed heuristic and not a validated ATS score. Heading detection may miss unusual section names. Keyword comparison can flag generic or irrelevant words. The prototype does not include OCR for scanned PDFs, robust passive-voice detection, a database, or a production-grade frontend/backend separation.

## 9. Conclusion
The prototype demonstrates a practical application of NLP for resume feedback by combining document text extraction, grammar checking, rule-based analysis, and TF-IDF text similarity. It can be extended with more accurate skill extraction, entity analysis, stronger evaluation, and a formatted report.

## 10. Future Work
- Named Entity Recognition and part-of-speech analysis in the results.
- More reliable skills taxonomy and semantic matching.
- Better readability and passive-voice analysis.
- PDF report export and optional database history.
- Automated unit tests and user evaluation.
