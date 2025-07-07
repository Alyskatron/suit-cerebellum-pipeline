# Cerebellum SUIT Processing Pipeline

This repository contains a MATLAB script for automating the preprocessing of cerebellar MRI data using the [SUIT toolbox](http://www.diedrichsenlab.org/imaging/suit.htm) (Spatially Unbiased Infratentorial Template). The pipeline includes segmentation, normalization, reslicing, atlas-based ROI extraction, and registration to R2* images using ANTs.

---

## 🧠 Overview

This script was developed to support neuroimaging analysis of cerebellar structures in structural MRI scans, especially when aligned with SWI/R2* images. It handles batch processing for multiple subjects and integrates with:

- **SPM12**
- **SUIT toolbox**
- **ANTs (Advanced Normalization Tools)**
- **FSL (for ROI statistics)**

---

## 🗂️ Directory Structure
## ⚙️ Requirements

- MATLAB (R2018 or later recommended)
- SPM12: https://www.fil.ion.ucl.ac.uk/spm/software/spm12/
- SUIT toolbox: http://www.diedrichsenlab.org/imaging/suit.htm
- ANTs: https://github.com/ANTsX/ANTs
- FSL (for `fslstats`): https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/

Ensure all tools are added to your system `PATH` or MATLAB environment appropriately.

---

## 🚀 How to Run

1. Update the `base_path` and `spm_path` variables in `cerebellum_suit_pipeline.m` to match your environment.
2. Make sure all dependencies (SPM, SUIT, ANTs, FSL) are installed and accessible.
3. In MATLAB:
    ```matlab
    cd /path/to/project
    cerebellum_suit_pipeline
    ```

The script will automatically:

- Segment the cerebellum from T1 images
- Normalize to SUIT space
- Reslice and inverse-reslice atlas regions
- Register to R2* space
- Extract ROI-wise mean R2* values using FSL

---

## 📤 Output

For each subject, the pipeline generates:

- Isolated cerebellum images (`c_T1_reorient_pcereb.nii`)
- Normalized/resliced images (`wdT1_reorient.nii`, etc.)
- Atlas-aligned maps in subject space
- Registered T1 to R2* image (`T1_2_R2.nii`)
- ROI summary: `R2_Lobules.txt`

---

## 📜 License

This project is open-source and available under the [MIT License](LICENSE).

---

## 🙋 Contributing

Pull requests and suggestions are welcome. Please submit an issue for discussion or enhancement ideas.

---

## 🧬 Acknowledgements

- [Christian Diedrichsen](http://www.diedrichsenlab.org/) for the SUIT toolbox
- ANTs developers
- FSL developers
