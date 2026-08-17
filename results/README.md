# Results notes

The notebooks keep the saved outputs from the course project. The results here are mainly useful for showing that the full workflow was implemented and tested.

## TG-CDDPM reproduction

The reproduction notebook includes training outputs for the three-stage pipeline and an AM-Score evaluation on 1,000 generated peptide samples.

For the final sampling step, checkpoints released by the original TG-CDDPM authors were used because the models trained in this project did not run for the full training schedule of the paper. Because of this, the evaluation should not be presented as a direct comparison between my shortened training runs and the paper's final model.

The notebook evaluates generated samples using CAMP, IPPF-FE, and an amPEP-based prediction pipeline. The saved outputs are left in the notebook so the steps and results can be inspected directly.

## LitePep-Diff

LitePep-Diff was an experimental lightweight direction. Several training runs were tried and 1,000 generated peptides were evaluated with the available AMP predictors.

This part remained incomplete. In particular, one of the external evaluation pipelines had a model-loading/dependency problem in the saved run. The available numbers are therefore kept only as preliminary experiment records and are not reported here as a final benchmark.

## Large files

Full training logs, checkpoints, generated files, and raw datasets are not included in the repository. They were kept separately during the project to avoid making the repository unnecessarily large.
