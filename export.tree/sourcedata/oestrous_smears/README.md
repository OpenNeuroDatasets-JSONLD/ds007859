#Oestrpus Smear Vaginal Cytology Images

This directory contains raw microscopy images of vaginal smears taken from female subjects to determine estrus stage. 
Images were taken on an Olympus BX51 light microscope equipped with a DP23 camera. 

## File Naming Convention
The images follow a BIDS-like naming structure to make automated parsing easier:
* **`sub-<ID>`**: Matches the participant ID.
* **`date-<YYYYMMDD>`**: The exact calendar date the smear was taken - please refer to the scan_date column in a subjects sessions.tsv file to determine the smears from days were an MRI was carried out.
* **`acq-<Magnification>`**: The objective magnification used on the microscope (all images were captured at 20x).

## Method
Slides were stained using Wright's stain, modified- see publication for further details


