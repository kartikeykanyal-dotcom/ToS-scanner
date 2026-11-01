# ToS-Scanner

**Read the red flags before you click "I agree".**

ToS-Scanner is an NLP-based unfair clause extractor for Terms of Service. It reads an agreement, splits it into sentences and highlights the ones that look like known unfair clauses: unilateral changes, arbitrary termination, forced arbitration, broad data sharing, hidden fees and more.

This repository holds the project website (`index.html`), a single self-contained page with a live browser demo.

**Live site:** https://kartikeykanyal-dotcom.github.io/ToS-scanner/

## Try the demo

Open the site, then paste text or upload a PDF, `.txt` or `.md` file. Use `sample-terms.pdf` or `sample-terms.txt` from this repo for a quick test. Move the threshold slider to see how it changes the flagged list.

The website demo matches phrases in your browser to illustrate the interface. The project itself uses a trained TF-IDF + logistic regression model in Python, so scores differ.

## How the project works

1. Input: pasted text or PDF
2. Text extraction (PyPDF2)
3. Cleaning and normalisation
4. Sentence segmentation (spaCy)
5. TF-IDF features (unigrams and bigrams)
6. Classification (class-weighted logistic regression)
7. Threshold filter (P > T)
8. Red-flag report in a Streamlit interface

All processing is local, so documents are never sent to an external service.

## Run the Python project locally

```bash
python -m venv venv
pip install -r requirements.txt
python -m spacy download en_core_web_sm
python train.py
pytest
streamlit run app.py
```

## Author

Kartikey Singh Kanyal, University Roll No. 2106164
Bachelor of Computer Applications (AI & DS), Graphic Era (Deemed to be University), Dehradun
Guide: Shiwani Bhaskar, Mentor. October 2026.

*Output is informational and is not legal advice.*
