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

I have used the BraTS2020 dataset for this work. It has 369 items for training and 125 items for validating. Each item has 5 .nii type files. They contain native, post-contrast, T2-weighted, T2-FLAIR volumes and one segmentation file. Segmentation file contains 3 types of annotations: enhancing tumor, peritumoral edema, and tumor core.




<!-- USAGE EXAMPLES -->
## Usage

Use this space to show useful examples of how a project can be used. Additional screenshots, code examples and demos work well in this space. You may also link to more resources.
* From "Desktop" tab, click on "Organize"  to organize your desktop folder.

![desktophome](https://user-images.githubusercontent.com/69592754/191538086-dafc203d-d353-4747-9998-e9f627a919a0.png)

* From "Others" tab, click on "Choose" button to choose a folder and click on "Organize" button to organize that folder.

![othertab](https://user-images.githubusercontent.com/69592754/191538941-ac8a1d4a-b9ea-452a-8c8c-0b3256e266f7.png)

## How it works
* This is the unorganized and dirty desktop folder.
![Web 1920 – 1](https://user-images.githubusercontent.com/69592754/191548398-081a2f0e-3746-49c2-8267-e8f3799a4877.png)

* After running desktop manager, the desktop folder will look like this. Organized according to their file types and clean.
![Web 1920 – 2](https://user-images.githubusercontent.com/69592754/191548442-7018993b-e895-4a1b-8351-ca06640ea8e6.png)


## Cautions
If you choose any other folder rather than the desktop folder, make sure you dont have any program files in that folder.


<!-- Contributors -->
## Contributors

<a href="https://github.com/AbduzZami/DesktopManagerCustom/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=AbduzZami/DesktopManagerCustom" />
</a>


<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

<a href="https://docs.github.com/en/get-started/quickstart/contributing-to-projects" target="_blank">See how to contribute to a project</a>



<!-- FAQ -->
## Tools

For my project, I utilized a variety of tools to facilitate the implementation and analysis of my deep learning model for medical image segmentation. Firstly, I employed the Nilearn library for its functionality in handling and visualizing neuroimaging data, particularly NIfTI files. This allowed seamless manipulation and exploration of the MRI data crucial for my project. Additionally, I leveraged the Segmentation Models 3D and Classification Models 3D libraries to access pre-built architectures and utilities tailored for 3D medical image segmentation and classification tasks. These libraries provided efficient implementations of state-of-the-art neural network architectures, streamlining the development process of my deep learning model. Visualkeras was another invaluable tool utilized for visualizing the architecture of my neural network models, aiding in understanding the model's structure and facilitating communication of the model design. Moreover, standard libraries such as NumPy, scikit-learn, and Matplotlib were employed for data preprocessing, model evaluation, and result visualization, ensuring robustness and interpretability of the project outcomes. Overall, these tools collectively enabled the seamless development, evaluation, and interpretation of my deep learning-based medical image segmentation project.


