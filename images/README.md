# Brain Tumor Classification from MRI Images using Classical Machine Learning and EfficientNetB0 Transfer Learning
This project focuses on the classification of brain tumors from MRI images using both **classical machine learning algorithms** and **deep learning techniques**.  
In addition to traditional ML models, a **transfer learning–based EfficientNetB0** architecture was implemented and evaluated to improve classification performance.

## Objectives
- Automatically classify brain tumors from MRI images  
- Compare classical machine learning models with deep learning approaches  
- Analyze the impact of **EfficientNetB0 transfer learning** on performance  

 ## Dataset
 **Source:** [https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset]
 
 **Total Images:** 7,023

 **Classes:** Glioma, Meningioma, Pituitary, No Tumor

 ## Sample MRI Images
 ![](images/sampleMRIimages.png)

 ## Methodology
1. Image preprocessing (resizing, normalization)  
2. Data augmentation to improve generalization  
3. Feature extraction and training using classical ML models (Logistic Regression, KNN, SVM, Naive Bayes, Decision Tree, AdaBoost, Random Forest)  
4. Transfer learning with **EfficientNetB0**
5. The models were evaluated using both hold-out validation and k-fold cross-validation.  
6. Performance evaluation and comparison

## Results (Top 2 Models)

| Model | Hold-Out Acc | Hold-Out F1 | K-Fold Acc | K-Fold F1 |
|------|-------------|-------------|------------|-----------|
| Random Forest | 0.933 | 0.928 | 0.925 | 0.922 |
| EfficientNetB0 | **0.947** | **0.943** | **0.908** | **0.904** |



## Training Performance
![Training Loss](images/loss_curve.png)

The training and validation accuracy curves show a consistent improvement over epochs, while the loss curves decrease steadily. 
The close alignment between training and validation results indicates stable learning without significant overfitting.

 ## Project Report
📎 **Full Project Report (Turkish):**  
[Brain Tumor Analysis Report (PDF)](report/Brain_Tumor_Analysis_Report_TR.pdf)

## Author
**Muhammed Doğru**  
Computer Engineering Student

## Setup on Windows (VS Code)

### 1. Install Python

Use **64-bit Python 3.13** from the [official Python downloads](https://www.python.org/downloads/windows/). In the installer, enable **Add python.exe to PATH**. TensorFlow's official installation guide lists support through Python 3.13.

### 2. Create the project environment

Open this project folder in VS Code. In **Terminal → New Terminal**, run each command separately:

```powershell
python -m venv .venv
```

```powershell
.\.venv\Scripts\python.exe -m pip install --upgrade pip
```

```powershell
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
```

In VS Code, use **Ctrl+Shift+P → Python: Select Interpreter**, then choose `.venv`. In each notebook, choose the `.venv` Python kernel.

### 3. Add the dataset

The dataset is not included in this repository. Download it from the [Brain Tumor MRI Dataset on Kaggle](https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset), extract it into this project folder, and make sure the folders `Training` and `Testing` are beside this README. Each should contain the four class folders: `glioma`, `meningioma`, `notumor`, and `pituitary`.

The notebooks currently use the relative folder names `Training` and `Testing`.

### 4. Open and run the notebooks

Open `notebooks/classical_ml_models.ipynb` for the classical models or `notebooks/cnn_efficientnetb0.ipynb` for EfficientNetB0. Select the `.venv` kernel before running cells. The EfficientNet notebook downloads pretrained ImageNet weights the first time it runs, so an internet connection is needed.

## Project structure

```text
images/       Sample MRI and training-curve images
notebooks/    Classical ML and EfficientNetB0 notebooks
report/       Project report (Turkish)
README.md     Project overview and setup instructions
requirements.txt
```

The dataset, virtual environment, and generated model checkpoints are excluded from Git by `.gitignore`.
