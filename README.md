# SynthUterus: Diffusion-Based Synthetic Uterine MRI Generation

## Overview

SynthUterus is a research framework for generating anatomically realistic synthetic uterine MRI scans using diffusion models. The project addresses the critical shortage of publicly available pelvic MRI datasets, which limits the development of reliable AI tools for gynaecological imaging.

By leveraging Denoising Diffusion Probabilistic Models (DDPMs) and Latent Diffusion Models (LDMs), we generate high-quality 2D and 3D uterine MRI images that can be used for data augmentation, clinical education, and downstream machine learning tasks such as anatomical classification.

---

## Motivation

- Public uterine MRI datasets are scarce due to privacy and data-sharing restrictions  
- High anatomical variability makes model training difficult with small cohorts  
- Diagnostic interpretation is often observer-dependent  
- Synthetic data can support education, algorithm development, and bias reduction  

Generative models provide a practical path toward scalable, privacy-preserving data creation for this underrepresented domain.

### Key Contributions

1. A diffusion-based framework for synthesising uterine MRI images in 2D and 3D  
2. Conditional generation using anatomical class labels and structured text prompts  
3. ROI-focused generation for clinically relevant image regions  
4. Privacy filtering to prevent memorisation of training data  
5. Evaluation on image quality metrics and clinical classification tasks  

---

## **Datasets**

The synthetic dataset **SynthUterus ROI** generated in this project is publicly available on Zenodo:

[https://zenodo.org/records/18297879](https://zenodo.org/records/18297879)

The synthetic datasets **SynthUterus 2D/3D** are coming soon!

---

## Methods

### Models

- DDPMs trained to reverse a fixed noising process and generate images from learned distributions  
- Latent Diffusion Models (LDMs) for high-resolution generation in a compressed latent space  
- Conditioning via class labels (uterine position) and descriptive text prompts  

### Preprocessing

- Bias field correction and intensity normalisation  
- Automatic uterus localisation and ROI extraction  
- Standardised in-plane resolution  
- Support for both full pelvic scans and uterus-focused crops  

### Privacy Safeguards

Generated images are filtered using perceptual similarity checks to avoid near-duplicates of training samples, reducing re-identification risks.

---

## Evaluation

- **Quality Metrics:** Fréchet Inception Distance (FID) and LPIPS  
- **Downstream Task:** Uterine position classification using ResNet-18  
- Synthetic datasets improved performance in weak-supervision settings and were difficult for clinicians to distinguish from real images.

## Results Summary

- Conditioning with anatomical labels and text improves generation quality  
- ROI-focused synthesis yields the best perceptual and task performance  
- Synthetic data can match or surpass real data in low-label regimes  
- 2D models currently outperform 3D models in quality and efficiency  

---

## Usage

The repository includes:

- Training scripts for DDPM and LDM models  
- Preprocessing pipelines for pelvic MRI  
- Generation and privacy-filtering utilities  
- Evaluation code for image quality and classification tasks  

---



## Licence

The code and generated datasets are released for research use under an open licence as specified in the Zenodo record.
Creative Commons Attribution 4.0 International (CC BY 4.0)

---

For questions or collaboration, please contact the authors.

## Citation

```
@InProceedings{10.1007/978-3-032-05825-6_9,
author="M{\"u}ller, Johanna P.
and Knupfer, Anika
and Bl{\"o}ss, Pedro
and Vittur, Edoardo Berardi
and Kainz, Bernhard
and Hutter, Jana",
title="Diffusing the Blind Spot: Uterine MRI Synthesis with Diffusion Models",
booktitle="Skin Image Analysis, and Computer-Aided Pelvic Imaging for Female Health",
year="2026",
publisher="Springer Nature Switzerland",
address="Cham",
pages="93--102",
isbn="978-3-032-05825-6"
}
```


