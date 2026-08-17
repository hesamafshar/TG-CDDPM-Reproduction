# Data notes

This repository does not include the full raw or processed datasets.

There are two different data parts in the project.

## 1. Original TG-CDDPM data

The TG-CDDPM reproduction uses the dataset and checkpoints released for the original paper. These files were downloaded separately and stored in Google Drive during the Colab runs.

They are not copied into this repository. Please use the original TG-CDDPM repository and its data instructions if you want to reproduce that part of the project.

## 2. Additional ACP data

For a possible extension, additional anticancer peptide data were collected from three sources:

- **CancerPPD2** — retrieved through its public API.
- **DRACP** — downloaded from the public Figshare files used by the database.
- **DCTPep** — downloaded from the dataset download page.

The extraction steps are in `notebooks/0-DataExtractionACP.ipynb`.

The preprocessing steps are in `notebooks/1-PreprocessingACP.ipynb`. The notebook:

- removes unusable sequences and keeps the sequence-length range used in the project,
- converts sequences to uppercase,
- builds text descriptions from the biological and structural fields available in each source,
- combines the ACP sources,
- prepares a non-ACP set from a DRAMP spreadsheet used during the project,
- creates final train and test splits.

In the saved run, the combined ACP table contained **14,086 samples** before the final split. The final split shown in the notebook contains **11,268 training samples** and **2,818 test samples**.

## Why the datasets are not uploaded here

The source databases have their own access and reuse conditions. To avoid redistributing third-party data without checking each license in detail, this repository keeps the extraction and preprocessing code but not the dataset files themselves.
