# TG-CDDPM Reproduction and Peptide Data Exploration

This repository contains work from a Bioinformatics course project at the University of Tehran. The main part of the project is a reproduction of **TG-CDDPM**, a text-guided diffusion model for antimicrobial peptide generation.

We also worked on preparing an additional anticancer peptide (ACP) dataset and started an experimental lightweight model because the original TG-CDDPM pipeline was expensive to train. The lightweight model was not developed into a complete research study, so it is kept here as preliminary work rather than a finished method.

## What is included

- **TG-CDDPM reproduction:** setup, three-stage training workflow, sampling, and AM-Score evaluation.
- **ACP data extraction:** collection of peptide data from CancerPPD2, DRACP, and DCTPep.
- **ACP preprocessing:** cleaning sequences, building text descriptions, combining datasets, and creating train/test splits.
- **LitePep-Diff:** an unfinished attempt to build a lighter peptide-generation model for limited computational resources.

## Reproduction scope

The original TG-CDDPM method has three main stages. In this project, I reproduced the workflow and trained the stages as far as the available resources allowed.

- **Stage 1:** trained for 50 epochs on the full released dataset. This run took about 17 hours.
- **Stage 2:** the training loop was not available in the original repository, so I wrote the loop in the notebook. This stage was trained for 10 epochs because of time and compute limits.
- **Stage 3:** the conditional diffusion stage was set up and trained for a shorter run. A few code changes were needed for conditioning and dataset paths.
- **Sampling:** checkpoints released by the original authors were used for the final sampling step because my own models were not trained for the full schedule used in the paper.

For this reason, the saved results should be read as a **reproduction and implementation study under limited computational resources**, not as an exact end-to-end replication of the paper's final benchmark.

## Additional ACP data

For a possible extension of the original project, we collected and processed additional anticancer peptide data from:

- CancerPPD2
- DRACP
- DCTPep

The preprocessing notebook converts the available biological information into text descriptions paired with peptide sequences. After cleaning and combining the sources, the saved run produced 14,086 ACP samples before the final train/test split. The notebook also prepares a non-ACP comparison set from a DRAMP file and creates the final training and test files.

The raw datasets are **not redistributed in this repository**. The extraction/preprocessing notebooks show how the data were obtained and processed.

## Experimental lightweight model

`LitePep-Diff` was started as an attempt to replace the heavier TG-CDDPM pipeline with a smaller model that could be trained with fewer computational resources. Some training runs and evaluation code were completed, but the idea was not developed into a complete comparison or publication-ready study.

I keep it in the repository because it shows the direction we explored after the reproduction work, but the results should be treated as preliminary.

## Repository structure

```text
TG-CDDPM-Reproduction/
├── README.md
├── notebooks/
│   ├── TG-CDDPM-Reproduction.ipynb
│   ├── 0-DataExtractionACP.ipynb
│   └── 1-PreprocessingACP.ipynb
├── experimental/
│   └── LitePep-Diff.ipynb
├── data/
│   └── README.md
├── results/
│   └── README.md
└── .gitignore
```

## Notes on running the notebooks

The notebooks were originally developed in Google Colab and some paths still follow the Drive structure used during the project. These paths may need to be changed before running the notebooks in a different environment.

The public notebook versions keep the original code and saved execution outputs. Only explanatory Markdown and notebook metadata are cleaned for readability and privacy.

## Contributors

- **Hesam Afshar**
- **Shaghayegh Roozmeh**

Bioinformatics course project, University of Tehran  
Instructor: **Dr. Kaveh Kavousi**

## Original work

This project is based on the paper:

**TG-CDDPM: Text-guided antimicrobial peptides generation based on conditional denoising diffusion probabilistic model**

Original implementation: [JunhangCao/TG-CDDPM](https://github.com/JunhangCao/TG-CDDPM)

The original TG-CDDPM code, checkpoints, datasets, and the external evaluation tools used in the notebooks remain under their own repositories and licenses.
