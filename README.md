<div align="center">

  
  <h1>Brain Tumor Segmentation using 3D-Unet</h1>
  
  
<!-- Badges -->
<p>
  <a href="https://github.com/AbduzZami/Brats2020-Segmentation-using-3DUnet/graphs/contributors">
    <img src="https://img.shields.io/github/contributors/Louis3797/awesome-readme-template" alt="contributors" />
  </a>
  <a href="">
    <img src="https://img.shields.io/github/last-commit/AbduzZami/Brats2020-Segmentation-using-3DUnet" alt="last update" />
  </a>
  <a href="https://github.com/AbduzZami/Brats2020-Segmentation-using-3DUnet/network/members">
    <img src="https://img.shields.io/github/forks/AbduzZami/Brats2020-Segmentation-using-3DUnet" alt="forks" />
  </a>
  <a href="https://github.com/AbduzZami/Brats2020-Segmentation-using-3DUnet/stargazers">
    <img src="https://img.shields.io/github/stars/AbduzZami/Brats2020-Segmentation-using-3DUnet" alt="stars" />
  </a>
  <a href="https://github.com/AbduzZami/Brats2020-Segmentation-using-3DUnet/issues/">
    <img src="https://img.shields.io/github/issues/AbduzZami/Brats2020-Segmentation-using-3DUnet" alt="open issues" />
  </a>
  <a href="https://github.com/AbduzZami/Brats2020-Segmentation-using-3DUnet/LICENSE">
    <img src="https://img.shields.io/github/license/AbduzZami/Brats2020-Segmentation-using-3DUnet" alt="license" />
  </a>
</p>
 
   

</div>

<br />



<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#introduction">Introduction</a>
    </li>
    <li>
      <a href="#objectives">Objectives</a>
      </li>
    <li><a href="#usage">Functions</a></li>
    <li><a href="#language-and-tools-with-justifications">Language & Tools</a></li>
    <li><a href="#methodology">Methodology</a>
      <ul>
          <li><a href="#dataset">Dataset</a></li>
          <li><a href="#preprocessing">Preprocessing</a></li>
          <li><a href="#modelcreation">Model Creation</a></li>
          <li><a href="#training-and-evaluation">Training and Evaluation</a></li>
      </ul>
    </li>
    <li><a href="#scores">Scores</a></li>
    <li><a href="#future-works">Future Work</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## Introduction

BraTS 2020 focuses on brain tumor segmentation in MRI scans, evaluating methods for glioma segmentation, patient survival prediction, progression status assessment, and segmentation uncertainty estimation. Data include multi-institutional MRI scans with manual tumor segmentations and clinical information. Scans cover native, post-contrast, T2-weighted, and T2-FLAIR volumes. Annotations include enhancing tumor, peritumoral edema, and tumor core. My job was to automate the segmentation process by using U-NET.

<!-- Objectives -->
## Objectives

1. Creating a UNET architecture that can generate segmented 3D mask images containing 3 types of annotations i.e. enhancing tumor, peritumoral edema, and tumor core.
2. Enhancing Dice Coefficient, IoU score, precision, recall, and F1-score.
3. Surpass related works on it.


<!-- Functions -->
## Functions

From any 3D MRI of the brain, this trained model can generate segmentation containing 3 types of annotations i.e. enhancing tumor, peritumoral edema, and tumor core.

## Language and Tools with Justifications

- Python: Programming language used for the project.
- Nilearn: Library utilized for handling and visualizing neuroimaging data, especially NIfTI files.
- Segmentation Models 3D: Libraries accessed for pre-built architectures and utilities tailored for 3D medical image segmentation and classification tasks.
- Visualkeras: Tool employed for visualizing the architecture of neural network models.
- NumPy, scikit-learn, Matplotlib: Standard libraries used for data preprocessing, model evaluation, and result visualization.

## Methodology

This work has been performed with a publicly available dataset. My methodology includes preprocessing, model creation, and evaluation techniques.

### Dataset

I have used the BraTS2020 dataset for this work. It has 369 items for training and 125 items for validating. Each item has 5 .nii type files. They contain native, post-contrast, T2-weighted, T2-FLAIR volumes and one segmentation file. Segmentation file contains 3 types of annotations: enhancing tumor, peritumoral edema, and tumor core. Each .nii file has a shape of (240, 240, 155).

### Preprocessing

I needed to preprocesses MRI images from the BraTS dataset, which includes T1, FLAIR, and T1CE modalities, along with corresponding segmentation masks. 

The preprocessing steps include:
1. Loading MRI images and segmentation masks from NIfTI files.
2. Normalizing intensity values of each modality using Min-Max scaling.
3. Converting segmentation masks into one-hot encoded categorical labels.
4. Cropping images and segmentation masks to a smaller size (128x128x128xF) to fit into GPU memory.

### Model Creation

![Unet 3D Brats](https://github.com/AbduzZami/Brats2020-Segmentation-using-3DUnet/assets/69592754/1a50cad9-952c-4517-95ec-0ef0e8f5a9c1)

### Training and Evaluation

To reduce the required time for training and evaluating, I just worked on the Training Folder of the above dataset. I split the Training Folder into train(80%) and test(20%). I further split the train set into train(80%) and validation(20%).

I trained the model for 50 epochs with a batch size of 1.

For evaluation metrics I used Dice Coefficient, Intersection over Union, Accuracy, Precison, Recall, and F1-score. But only the Dice Coefficient and Intersection over Union is meaningful here.

Below are the scores for different labels.

|           | Dice Score | IoU Score |
|-----------|------------|-----------|
| Label 0   | 99         | 99        |
| Label 1   | 80         | 89        |
| Label 2   | 60         | 55        |
| Label 3   | 24         | 24        |
| Label 4   | 24         | 24        |


