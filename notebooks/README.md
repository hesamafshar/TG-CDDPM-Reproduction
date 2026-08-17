# Notebooks

This folder contains the main reproduction and data-preparation notebooks used in the project.

## `TG-CDDPM-Reproduction.ipynb`

Main reproduction notebook. It follows the three-stage TG-CDDPM workflow, includes the shortened training runs used in the course project, sampling, and AM-Score evaluation.

The public copy keeps the original code cells and saved outputs. The explanatory Markdown was rewritten in English, and personal Colab metadata was removed.

## `0-DataExtractionACP.ipynb`

Collects additional anticancer peptide data from CancerPPD2 and DRACP. The DCTPep source used in the project is also documented in this notebook.

## `1-PreprocessingACP.ipynb`

Cleans and combines the ACP sources, builds text descriptions from the available biological fields, prepares a non-ACP comparison set, and creates train/test splits.

The notebooks were developed in Google Colab, so some local Drive paths may need to be changed before running them elsewhere.
