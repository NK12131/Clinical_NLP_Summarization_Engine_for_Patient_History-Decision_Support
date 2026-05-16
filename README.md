# Clinical NLP Summarization Engine for Patient History & Decision Support

> An end-to-end NLP pipeline that auto-generates concise, clinically relevant summaries from lengthy patient histories using transformer-based models — built to reduce information overload and support faster, data-driven clinical decisions.

---

##  Overview

Built an NLP pipeline using **T5** and **BART** transformer models to automatically generate concise summaries from patient histories, integrating **medical Named Entity Recognition (NER)** to extract key clinical entities. Evaluated model performance using **ROUGE** and **BLEU** scores and deployed a **web-based interface** for clinical decision support.

---

##  Key Features

- **Abstractive & Extractive Summarization** — leverages T5 and BART seq2seq architectures to generate human-readable, context-aware summaries
- **Medical NER Integration** — identifies and extracts key clinical entities (diagnoses, medications, procedures) to ensure summary relevance
- **Multi-Metric Evaluation** — benchmarked using ROUGE-1, ROUGE-2, ROUGE-L, and BLEU scores for structural and semantic accuracy
- **Web-Based Demo Interface** — interactive UI for clinical teams to input patient notes and retrieve instant summaries
- **Clinical Decision Support Focus** — designed for healthcare product teams to reduce documentation burden and accelerate decision-making

---

##  Architecture

```
Patient History Input
        │
        ▼
  Text Preprocessing
  (Tokenization, Cleaning)
        │
        ▼
Medical NER Pipeline ──► Entity Extraction
(Diagnoses, Medications,    (Structured Metadata)
 Procedures, Symptoms)
        │
        ▼
Summarization Models
  ├── T5-Base (fine-tuned)
  └── BART-Base (fine-tuned)
        │
        ▼
Evaluation Layer
  ├── ROUGE-1 / ROUGE-2 / ROUGE-L
  └── BLEU Score
        │
        ▼
  Web Interface Output
  (Clinical Summary + Key Entities)
```

---

##  File Structure

```
├── notebooks/
│   ├── BART_BASE_Summarization.ipynb       # Fine-tuning BART-Base model
│   ├── T5_BASE_Summarization.ipynb         # Fine-tuning T5-Base model
│   └── Model_Evaluation.ipynb              # ROUGE & BLEU evaluation on test set
├── src/
│   ├── ner_pipeline.py                     # Medical NER entity extraction
│   ├── summarizer.py                       # Inference pipeline for T5 & BART
│   └── app.py                              # Web interface (Flask/Streamlit)
├── data/
│   └── sample_patient_notes/               # De-identified sample inputs
├── requirements.txt
└── README.md
```

---

##  Models & Evaluation

| Model | ROUGE-1 | ROUGE-2 | ROUGE-L | BLEU |
|-------|---------|---------|---------|------|
| T5-Base (fine-tuned) | — | — | — | — |
| BART-Base (fine-tuned) | — | — | — | — |

> *Populate with your actual scores after evaluation.*

---

##  Tech Stack

| Layer | Tools |
|-------|-------|
| Summarization Models | T5, BART (HuggingFace Transformers) |
| NER | spaCy / scispaCy / medspaCy |
| Evaluation | ROUGE, BLEU (datasets, nltk) |
| Web Interface | Streamlit / Flask |
| Language | Python 3.9+ |

---

##  Setup & Installation

```bash
# Clone the repository
git clone https://github.com/your-username/clinical-nlp-summarization.git
cd clinical-nlp-summarization

# Install dependencies
pip install -r requirements.txt

# Run the web interface
streamlit run src/app.py
```

---

##  Use Case

Healthcare professionals face significant documentation burden — patient histories can span dozens of pages. This system:

1. Ingests raw clinical notes or patient history text
2. Extracts key medical entities via NER (diagnoses, medications, symptoms)
3. Generates a concise, abstractive summary using fine-tuned T5 or BART
4. Surfaces the summary + structured entities through a web interface for clinical review

---

## Dataset

- **Primary:** [PubMed Summarization Dataset](https://huggingface.co/datasets/ccdv/pubmed-summarization) (HuggingFace)
- **NER:** Trained on clinical corpora using scispaCy biomedical models
- All patient data used is de-identified and PII-compliant

---

##  Future Work

- Fine-tune on MIMIC-III clinical notes for higher domain specificity
- Integrate BERT Score for semantic evaluation beyond n-gram overlap
- Expand NER to cover social determinants of health (SDOH) entities
- Explore retrieval-augmented summarization (RAG) for evidence grounding

---

##  Author

**Nithin Kumar**
📧 nithink12131@gmail.com | 🌐 [nithinkumar.vercel.app](https://nithinkumar.vercel.app) | 🔗 [LinkedIn](https://linkedin.com/in/your-profile)