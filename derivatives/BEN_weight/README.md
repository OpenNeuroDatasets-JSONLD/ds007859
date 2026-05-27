#BEN - BRAIN EXTRACION NET
https://github.com/yu02019/BEN/tree/main/dataset_release#2.0

@article{yu2022generalizable,
  title={A generalizable brain extraction net (BEN) for multimodal MRI data from rodents, nonhuman primates, and humans},
  author={Yu, Ziqi and Han, Xiaoyang and Xu, Wenjing and Zhang, Jie and Marr, Carsten and Shen, Dinggang and Peng, Tingying and Zhang, Xiao-Yong and Feng, Jianfeng},
  journal={Elife},
  volume={11},
  pages={e81217},
  year={2022},
  publisher={eLife Sciences Publications Limited}
}


## Methodology & Parameters
to create the this weight, domain adaption was carried out using the available pretrained Rat-T2WI-9.4T weight on github as the reference. This weight has similar parameters to STANDARDRAT, so was used for that reason. 


The following scans were manually masked by DMcL and used as the training set for domain adaption.
The aim was to make the new weight genreralisable across age, sex and experimental run.
These scans were chosen to ensure training used 20 male and 20 female scans; ensure it was trained on 8 ses-1, 8 ses-2, 8 ses-3, 8 ses-4 and 8 ses-5 scans; and have 2 subjects from each experimental runs

sub-2023080404_ses-1
sub-2023080405_ses-1
sub-2023090102_ses-1
sub-2023090103_ses-1
sub-2024011502_ses-1
sub-2024011503_ses-1
sub-2024021402_ses-1
sub-2024021403_ses-1
sub-2023080404_ses-1
sub-2023080405_ses-2
sub-2023090102_ses-2
sub-2023090103_ses-2
sub-2024011502_ses-2
sub-2024011503_ses-2
sub-2024021402_ses-2
sub-2024021403_ses-2
sub-2023080404_ses-2
sub-2023080405_ses-3
sub-2023090102_ses-3
sub-2023090103_ses-3
sub-2024011502_ses-3
sub-2024011503_ses-3
sub-2024021402_ses-3
sub-2024021403_ses-3
sub-2023080404_ses-4
sub-2023080405_ses-4
sub-2023090102_ses-4
sub-2023090103_ses-4
sub-2024011502_ses-4
sub-2024011503_ses-4
sub-2024021402_ses-4
sub-2024021403_ses-4
sub-2023080404_ses-5
sub-2023080405_ses-5
sub-2023090102_ses-5
sub-2023090103_ses-5
sub-2024011502_ses-5
sub-2024011503_ses-5
sub-2024021402_ses-5
sub-2024021403_ses-5

### Step A: Domain Adaption
BEN_DA.py was run 

####Step B: Inference
BEN_infer.py was run 

##### Please see github for scripts to do the inference step


