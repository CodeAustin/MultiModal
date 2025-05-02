# MultiModal Dementia Analysis Model

This project involves three models used to analyze MRI and clinical data from the OASIS-1 dataset. All notebooks are configured such that, as long as the required libraries are installed, using the `Run All` command should execute without issues.

### Dataset

Ensure that the "Data" folder contains the following four categories in alphabetical order: `Mild Dementia`, `Moderate Dementia`, `Non Demented`, and `Very Mild Dementia`. If this folder is empty, please download the dataset from the following Kaggle link:
[https://www.kaggle.com/datasets/ninadaithal/imagesoasis/data](https://www.kaggle.com/datasets/ninadaithal/imagesoasis/data)

Also, ensure that the metadata file `oasis_cross-sectional.xlsx` is **not** inside the "Data" folder but located in the main working directory. If it is missing, download it from the official OASIS-1 website under the "Demographic and Clinical Data" tab, and rename it accordingly.

**OASIS-1**: [https://sites.wustl.edu/oasisbrains/home/oasis-1/](https://sites.wustl.edu/oasisbrains/home/oasis-1/)

### Library Installation

To install all necessary libraries, run the following command:

```bash
pip install -r requirements.txt
```

### `MultiModule.ipynb`

This notebook contains the MultiModule model, which combines a CNN module using ResNet-18 with a Sequential module based on a modified version of the standalone model found in `StandAloneSequential.ipynb`.
It is **highly recommended** to utilize CUDA or another form of GPU acceleration due to the significant computational demand from image processing.
**Note**: Do not set the number of epochs in the Sequential Module above 50, as this may result in an error.

### `DenseNet.ipynb`

This notebook implements a basic version of the DenseNet-121 architecture and serves as a baseline for the CNN module. It analyzes the MRI images and outputs a confusion matrix comparing predictions to ground-truth labels.

### `StandAloneSequential.ipynb`

This notebook contains a simple linear classifier that serves as the baseline for the Sequential module. It processes and evaluates the clinical data from the OASIS-1 dataset.

