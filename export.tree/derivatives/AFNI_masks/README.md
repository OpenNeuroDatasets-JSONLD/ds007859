# AFNI Strict Brain Masks

This directory contains strict binary brain masks generated for resting-state functional MRI data using AFNI (Analysis of Functional NeuroImages): https://afni.nimh.nih.gov/.

## Methodology & Parameters
The masks in this directory were generated from the RABIES preprocessed BOLD reference images using a two-step AFNI pipeline:

## Step A: Background Removal
To isolate the brain and remove background data, the RABIES BOLD reference image was multiplied by the initial RABIES brain mask using `3dcalc`.

3dcalc -a <bold_ref.nii.gz> -b <initial_mask.nii.gz> -expr "a*b" -prefix <masked_bold.nii.gz>

## Step B: Strict Intensity Thresholding (Clip Fraction)
A highly strict, intensity-based binary mask was then generated from the background-suppressed image using AFNI's 3dAutomask

3dAutomask -clfrac 0.3 -prefix <final_mask.nii.gz> -overwrite <masked_bold.nii.gz>

##### Please see scripts to do this step
