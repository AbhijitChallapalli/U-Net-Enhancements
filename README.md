# Brain MRI Tumor Segmentation using Enhanced U-Net Architectures

This repository presents a comparative study of four U-Net-based deep learning architectures—Basic U-Net, Attention U-Net, Residual U-Net, and U-Net++—applied to brain tumor segmentation using the LGG MRI dataset.

---

## Project Overview

The goal of this project is to segment tumor regions in FLAIR MRI scans of patients with low-grade glioma. We implement and compare:
- **Basic U-Net**: A classical encoder-decoder architecture.
- **Attention U-Net**: Incorporates attention gates to focus on relevant features.
- **Residual U-Net**: Adds residual connections to improve training stability.
- **U-Net++**: Uses nested dense skip pathways for better multiscale feature fusion.

---

##  Results Summary

| Model             | Avg. Dice Score | Comments |
|------------------|------------------|----------|
| Basic U-Net       | 0.6259           | Baseline model |
| Attention U-Net   | **0.6800**      | Best performance with attention gating |
| Residual U-Net    | 0.6446           | Stable convergence |
| U-Net++           | 0.6352           | High capacity but inconsistent |

Visualizations and comparison plots for training loss and Dice scores are included in the repo.

---

## Setup Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/BrainMRI-Segmentation.git
cd BrainMRI-Segmentation
```

### 2. Set Up Environment
Use Google Colab (recommended) or install locally:
```bash
pip install -r requirements.txt
```

### 3. Dataset
Download the BrainMRI.zip dataset from [Kaggle](https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset)  
Upload to your Google Drive and extract using the code in the notebook.

---

##  Training

Each model is trained for 10 epochs using Adam optimizer and a composite loss function:

- **Binary Cross Entropy (BCE) Loss**
- **Dice Loss**  
  Dice Score formula used:  
  \[
  	ext{Dice}(P, G) = rac{2 \cdot |P \cap G| + \epsilon}{|P| + |G| + \epsilon}
  \]

Threshold: `0.5` for converting prediction probabilities to binary masks.

---

## Visualizations

- Training Loss Curves
- Validation Dice Score Curves
- Side-by-side segmentation results (input, ground truth, predicted)

---

##  References

1. Ronneberger et al., U-Net: Convolutional Networks for Biomedical Image Segmentation, MICCAI 2015  
2. Oktay et al., Attention U-Net, arXiv:1804.03999  
3. He et al., Deep Residual Learning, CVPR 2016  
4. Zhou et al., UNet++, IEEE TMI 2019  
5. [Kaggle Dataset - LGG MRI](https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset)

---

## Contributions

Feel free to fork, submit issues, or propose enhancements. All feedback is welcome!

---

##  Future Work

- Training for more epochs  
- Using multi-modal inputs (e.g., T1 + FLAIR)  
- Deploying models via Streamlit or Gradio

---

## Contact

For questions, reach out to **Abhijit Challapalli** via [LinkedIn](https://www.linkedin.com/in/abhijit-c-b5876814b/) or **Omkar Desai** via [[LinkedIn]]()
