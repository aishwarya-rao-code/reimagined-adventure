# Cancer Staging Automation Pipeline

Hi there 👋 This project automates cancer staging classification using pathology reports from TCGA. It extracts, preprocesses, and classifies reports to identify if a case is upstaged, downstaged, likely downstaged, or needs clinical review.

---

## Project Objective

This pipeline helps analyze cancer pathology reports efficiently. It includes:

- Downloading TCGA reports
- Extracting text using OCR tools like AWS Textract
- Cleaning and preprocessing the text
- Applying clinical rules to classify reports
- Preparing for future extensions like stage type prediction models and medicine suggestion support

We aim to make staging faster, accurate, and ready for integration into clinical workflows.

---

## Pipeline Steps

1. **Data Download**  
   Download pathology reports from TCGA and store them in `data/raw`.

2. **Text Extraction**  
   Use OCR tools like AWS Textract to extract readable text from reports.

3. **Preprocessing**  
   Convert to lowercase, clean symbols, and extract numeric invasion percentages.

4. **Staging Classification**  
   - **Upstaging detection:** lymph node metastasis, high-grade tumors, distant metastasis
   - **Downstaging detection:** low grade, confined to uterus, <50% invasion, no LVSI
   - **Likely Downstaged:** partial criteria match with <50% invasion
   - **Conflict check:** both upstage and downstage indicators trigger clinical review
   - **No Change:** if none of the above are detected

5. **Outputs**  
   Saves categorized results for review and analysis.

---

## Folder Structure

| Folder/File | Description |
|-------------|-------------|
| `data/` | TCGA raw and processed files |
| `notebooks/` | Analysis notebooks |
| `outputs/` | Results and flowcharts |
| `src/` | Scripts for extraction, preprocessing, staging |
| `requirements.txt` | Python dependencies |
| `README.md` | Project documentation |

---

## How to Run

### Clone the repo

```bash
git clone https://github.com/yourusername/cancer-staging-pipeline.git
cd cancer-staging-pipeline
Install dependencies
Bash

pip install -r requirements.txt
Run the staging script
Bash

python src/staging_classification.py
⚠️ Notes
This repo contains no patient-identifiable data. Only public TCGA sample reports are used.

Outputs are for research and educational purposes.

Clinical decisions should always be verified by medical professionals.

✨ Key Features
Automated cancer staging classification

Upstaging and downstaging detection using clinical rules

Clean modular code for easy future integration

Future-ready structure for ML stage prediction and treatment suggestion

🚧 Future Work
Build a machine learning model for stage type prediction

Integrate treatment recommendation module with clinician feedback

Extend pipeline to other cancer types and staging guidelines

🙏 Acknowledgements
The Cancer Genome Atlas (TCGA) for public datasets

AWS Textract for OCR extraction

University of South Florida (USF)

Professor Templeton for guidance

Professor Ankur Mali for mentorship and support

🤝 Contributions
Open to improvements and extensions. Feel free to fork, submit pull requests, or raise issues to discuss ideas.

Thank you for checking out this project!
