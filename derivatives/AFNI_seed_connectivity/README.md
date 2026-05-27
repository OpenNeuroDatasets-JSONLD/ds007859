# AFNI Seed-Based Functional Connectivity Validation

This directory contains derived seed-to-voxel functional connectivity maps and extracted 1D timeseries used to validate the preprocessing and cleaning pipelines of this normative dataset.

## Maps Included (`statmap.nii.gz`)
For each defined Region of Interest (ROI), two spatial maps are provided:
* **`Rmap`**: Raw Pearson correlation coefficients (r) representing the correlation between the seed timeseries and every other voxel in the brain.
* **`Zmap`**: Fisher z-transformed correlation maps, normalized for group-level statistical analysis.
        
        3dTcorr1D \
            -prefix <z_map or r_map \
            -mask <brain_mask> \
            -overwrite \
            -Fisher \ # for z_map only, removed for r_map
            <confound_corrected_bold> \
            <seed_timeseries>


## Timeseries (`timeseries.tsv`)
The raw, 1D average BOLD timeseries extracted from the defined ROI mask generated using 3dmaskave

        3dmaskave \
            -quiet \
            -mask <seed.nii.gz> \
            <confound_corrected_bold> > <seed_timeseries>
