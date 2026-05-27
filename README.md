# Longitudinal Normative Rat fMRI Dataset

## 1. Overview
This dataset contains longitudinal resting-state functional MRI (rs-fMRI) and anatomical data from 36 Wistar rats (male and female). Each subject was scanned across 5 developmental timepoints (sessions) to establish a normative trajectory of brain network development. 

Data was acquired on a 7T Bruker scanner using an 8x1 rat head surface array coil.

## 2. Dataset Highlights
This dataset includes highly detailed phenotypic and physiological metadata to support rigorous statistical modeling:
* **Longitudinal Tracking:** Subject-varying parameters (age in days, body weight, respiration rate) are documented per session in the `sub-<ID>_sessions.tsv` files.
* **Developmental Milestones:** Exact days of puberty onset are provided for all subjects in the root `participants.tsv` file.
* **Vaginal Oestrous Smears:** Raw microscopy images of the vaginal smears provided in the `sourcedata/` directory.
* **Quality Control (QC):** Session-specific QC metrics (including mean Framewise Displacement and tSNR) are provided  in the `derivatives/RABIES` folder.

## 3. Directory Guide
Beyond the raw BIDS data, this dataset includes several derivatives generated during preprocessing. (Please see the individual `README.md` files within each derivative folder for exact methodology and parameters).

* **`sourcedata/`**: Contains raw `.jpg` microscopy images of oestrous smears.
* **`derivatives/population_template/`**: Contains the unbiased, study-specific optimized_antsMultivariateTemplateConstruction population templates (0.2mm and 0.3mm resolutions) and transformed ROIs used in technical validation (`tpl-normative`).
* **`derivatives/RABIES/`**: Contains the fully preprocessed, confound-corrected, and bandpass-filtered functional timeseries registered to the normative template (`space-normative`). This folder also contains the 'fd', 'motion' parameters and 'tsnr' files from RABIES
* **`derivatives/AFNI_masks/`**: Contains strict, intensity-thresholded binary brain masks used to replace the default RABIES masks during confound correction as default masks were found to include region without any signal.

## 4. Notes and Missing Data
* sub-2023080406 does not have ses-1 (P28) scan due to technical issues with the scanner
* A small number of physiological recordings (e.g., respiration rates for specific sessions) were lost or unrecorded due to hardware issues. These are  denoted as `n/a` in the `sessions.tsv` files.
* To control for batch and sibling effects, exact experimental wave numbers and litter IDs are provided in `participants.tsv`.

## 5. Citation and Contact
If you use this dataset or its derivatives in your research, please cite the accompanying manuscript:
* [Insert Paper Tirtle Here]
* [Insert DOI or Journal Link Here]

For questions regarding the dataset, pipelines, or templates, please contact:
* Daniel P. McLoone - mclooned@tcd.ie - Trinity College Institute of Neuroscience, Trinity College Dublin
