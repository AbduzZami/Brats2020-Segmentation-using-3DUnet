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
          <li><a href="#experimental-set-up">Experimental Set Up</a></li>
      </ul>
    </li>
    <li><a href="#scores">Scores</a></li>
    <li><a href="#contributors">Contributors</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## Introduction

A brain tumor is an abnormal growth of cells in the brain cells.
MRI scans are best for detecting brain tumors.
An automated brain tumor segmentation will help to open new era in the treatment of brain tumor.

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

I needed to preprocesses MRI images from the BraTS dataset, which includes T1, T2, FLAIR, and T1CE modalities, along with corresponding segmentation masks. 

The preprocessing steps include:
1. Loading MRI images and segmentation masks from NIfTI files.
2. Removed T2 image.
3. Normalizing intensity values of each modality using Min-Max scaling.
4. Converting segmentation masks into one-hot encoded categorical labels.
5. Segmentation image had four unique pixel values 0 (Nothing),1(Non-enhancing tumor core), 2(Edema), 3(Not Specified), 4(Enhancing tumor). 
Label 3 was replaced by label 4.
6. Cropping images and segmentation masks to a smaller size (128x128x128xF) to fit into GPU memory. Cropped Image = Original Image [56:184,56:184,13:141]

### Model Creation

![Unet 3D Brats](https://github.com/AbduzZami/Brats2020-Segmentation-using-3DUnet/assets/69592754/1a50cad9-952c-4517-95ec-0ef0e8f5a9c1)

### Experimental Set Up

To reduce the required time for training and evaluating, I just worked on the Training Folder of the above dataset. I split the Training Folder into train(80%) and test(20%). I further split the train set into train(80%) and validation(20%).

I trained the model for 50 epochs with a batch size of 1.

Loss function was totalloss=diceloss+(1*focalloss).

Learning rate was 0.001.

Optimizer was Adam.

Early Stopping was applied with patience 5 on validation loss.

For evaluation metrics I used Dice Coefficient, Intersection over Union, Accuracy, Precison, Recall, and F1-score. But only the Dice Coefficient and Intersection over Union is meaningful here.

## Scores

Below are the scores for different labels.

| Label     | Dice Score | IoU Score |
|-----------|------------|-----------|
| Label 0   | 98.97         | 98.05        |
| Label 1   | 55.20         | 44.59        |
| Label 2   | 62.26         | 49.98        |
| Label 3   | 62.17         | 51.94        |


<!-- Contributors -->
## Contributors

<a href="https://github.com/AbduzZami/Brats2020-Segmentation-using-3DUnet/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=AbduzZami/Brats2020-Segmentation-using-3DUnet" />
</a>


<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

<a href="https://docs.github.com/en/get-started/quickstart/contributing-to-projects" target="_blank">See how to contribute to a project</a>



<!-- LICENSE -->
## License

Distributed under the Apache License 2.0 License. See `LICENSE` for more information.
