# Enhanced BioBART for Radiology Report Summarization

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)  
[![Python 3.8+](https://img.shields.io/badge/python-3.8%2B-blue.svg)](https://www.python.org/)

## 📖 Project Overview

This repository contains our implementation of an **enhanced BioBART** model for abstractive summarization of radiology reports, fine-tuned on the radiology subset of the MIMIC-III dataset. We introduce structural tokens to denote report sections (e.g., Findings vs. Impression) and length-control tokens (`<SUM_SHORT>`, `<SUM_MEDIUM>`, `<SUM_LONG>`), and employ advanced training strategies—**Progressive Unfreezing** and **Curriculum Learning**—to optimize performance.

---

## ✨ Key Features

- **Domain-Adapted Model**  
  Based on the pre-trained BioBART model (`GanjinZero/biobart-v2-base`) for biomedical text.
- **Structural Tokens & Length Control**  
  Special tokens inserted to mark sections and guide summary length.
- **Advanced Training Strategies**  
  - *Progressive Unfreezing*: Gradual unfreezing of model layers across epochs  
  - *Curriculum Learning*: Gradual increase of training sample size every 3 epochs
- **Evaluation Framework**  
  - Standard metrics: ROUGE-1/2/L, BLEU  
  - Clinical metric: Clinical Entity Overlap (precision, recall, F1) using scispaCy

---

## 🚀 Quick Start

1. **Clone the repository**  
   ```bash
   git clone https://github.com/<YOUR-USERNAME>/enhanced-biobart-summarization.git
   cd enhanced-biobart-summarization

2. Install dependencies:
    
   pip install -r requirements.txt
   
4. Obtain MIMIC-III data
   
   Due to licensing restrictions, MIMIC-III cannot be shared in this repo.Apply for credentialed access via PhysioNet:https://physionet.org/content/mimiciii/1.4/Once approved, download and place the radiology notes.

6. Run the notebook
   
   Open and execute Enhanced_BioBART_Text_Summarization.ipynb in Jupyter or Colab.Adjust the DATA_PATH and MODEL_CACHE_DIR variables at the top as needed.

📂 Repository Structure

.
├── Enhanced_BioBART_Text_Summarization.ipynb   # Main implementation notebook
├── requirements.txt                            # Python dependencies
├── README.md                                   # ← this file
└── LICENSE                                     # MIT License for code

⚠️ Data Licensing

MIMIC-III (v1.4) is distributed under the PhysioNet Credentialed Health Data License and cannot be publicly redistributed.
This repository uses only the radiology subset; users must download and preprocess the data locally as described above.
