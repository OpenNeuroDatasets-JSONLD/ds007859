# Normative Population Template and ROIs (`tpl-normative`)

This directory contains the custom, unbiased population-average brain template and associated Regions of Interest (ROIs) used as the common spatial framework for this dataset. All functional data in the `RABIES` derivatives folder labeled with `space-normative` is registered to this template.

## 1. Template Generation (optimized_antsMultivariateTemplateConstruction)
The population template was generated using optimized_antsMultivariateTemplateConstruction, specifically the `twolevel_modelbuild.sh` script. 
* **Level 1 (Subject-Level):** For each of the 36 subjects, the 5 longitudinal structural scans were registered to create an unbiased within-subject average.
* **Level 2 (Population-Level):** The 36 unbiased subject averages were then iteratively registered to create this final, unbiased population average template.
Germann, J., Gouveia, F. V., Chakravarty, M. M. & Devenyi, G. A.
Longitudinal deformation-based morphometry pipeline to study neuroanatomical differences in structural MRI based on SyN unbiased templates.
Aperture Neuro 5, (2025).
http://dx.doi.org/10.52294/001c.133510
https://github.com/CoBrALab/optimized_antsMultivariateTemplateConstruction




## 2. Spatial Resolutions (`res-`)
To accommodate both high-resolution anatomical viewing and functional timeseries extraction, the template and masks are provided at two isotropic resolutions:
* **`res-02` (0.2 mm isotropic):** The high-resolution template space. (Note: Original in-plane resolution was 0.2mm, with 1mm slice thickness; this was upsampled to 0.2mm isotropic fo use as the template during preprocessing.
* **`res-03` (0.3 mm isotropic):** The functional resolution space. This matches the resampling resolution of the RABIES-cleaned functional BOLD data - this file was taken from RABIES.

## 3. Regions of Interest (ROIs)
A set of pre-defined ROIs were transformed into the 0.3mm `tpl-normative` space for targeted time-series extraction and connectivity analysis. These are provided as binary masks:
* `ACAl`: Anterior Cingulate Area (Left)
* `CPul`: Caudate Putamen (Left)
* `MOpl`: Primary Motor Area (Left)
* `S1bfl` / `S1bfr`: Primary Somatosensory Area, Barrel Field (Left/Right)
These seeds were created by Grandjean, J., Desrosiers-Gregoire, G., Anckaerts, C. et al. A consensus protocol for functional connectivity analysis in the rat brain. Nat Neurosci 26, 673–681 (2023). https://doi.org/10.1038/s41593-023-01286-8

These were orginally in the SIGMA rat template space but transformed into out normative commonspace
Barrière, D.A., Magalhães, R., Novais, A. et al. The SIGMA rat brain templates and atlases for multimodal MRI data analysis and visualisation. Nat Commun 10, 5699 (2019). https://doi.org/10.1038/s41467-019-13575-7



* `roi521`:Primary Somatosensory Cortex Barrel field-L, `roi522`:Primary Somatosensory Cortex Barrel field-R, `roi731`:Striatum-L, `roi732`:Striatum-R .

These seeds are from SIGMA atlas 1.2.1 (https://www.nitrc.org/projects/sigma_template) and have been used to validate cortical and subcortical tSNR
Please note as of publication, SIGMA v2.0 is the latest version:
https://zenodo.org/records/10635831

Grandjean, J., Desrosiers-Gregoire, G., Anckaerts, C. et al. A consensus protocol for functional connectivity analysis in the rat brain. Nat Neurosci 26, 673–681 (2023). https://doi.org/10.1038/s41593-023-01286-8

## 4. Brain Masks
Strict binary brain masks (`desc-brain_mask.nii.gz`) are provided for both the 0.2mm and 0.3mm templates. These were utilised during the RABIES preprocessing pipeline to constrain normalisation and confound correction to brain tissue only.

* **`from-normative_to-SIGMA_mode-image_xfm`**: ANTs transformation files (`.mat` and `.nii.gz`) to map the study-specific normative template into the standard SIGMA space for visualisation. The SIGMA template itself is not included.
