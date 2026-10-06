# Brain Tumor MRI Classification

This educational project compares classical machine-learning models with EfficientNetB0 transfer learning for classifying brain MRI images into four categories: glioma, meningioma, pituitary tumor, and no tumor.

**This project is for learning and research only. It is not clinically validated and must not be used to diagnose or guide medical care.**

## Project contents

- `notebooks/classical_ml_models.ipynb` — classical machine-learning models and evaluation
- `notebooks/cnn_efficientnetb0.ipynb` — EfficientNetB0 transfer learning
- `images/` — example images and a training curve
- `report/Brain_Tumor_Analysis_Report_TR.pdf` — report in Turkish
- `requirements.txt` — Python packages used by the notebooks

The notebooks expect the Kaggle dataset in `Training/` and `Testing/` folders next to this README. The dataset is not included in this repository.

## Dataset

Download the [Brain Tumor MRI Dataset from Kaggle](https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset). After extracting it, the project folder should contain:

```text
Training/
  glioma/
  meningioma/
  notumor/
  pituitary/
Testing/
  glioma/
  meningioma/
  notumor/
  pituitary/
```

The notebooks currently use the relative paths `Training` and `Testing`.

## Setup in VS Code on Windows

TensorFlow's current installation guide lists Python support through 3.13. Install 64-bit Python 3.13 from [Python.org](https://www.python.org/downloads/windows/) and enable **Add python.exe to PATH** in the installer.

Open this project folder in VS Code. From **Terminal → New Terminal**, run each command separately:

```powershell
python -m venv .venv
```

```powershell
.\.venv\Scripts\python.exe -m pip install --upgrade pip
```

```powershell
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
```

Then use **Ctrl+Shift+P → Python: Select Interpreter** and select `.venv`. In each notebook, choose the `.venv` Python kernel. The first EfficientNetB0 run needs internet access to download pretrained ImageNet weights.

## Running the notebooks

Run one notebook at a time:

1. `notebooks/classical_ml_models.ipynb`
2. `notebooks/cnn_efficientnetb0.ipynb`

The accuracy and F1 values shown below are the results reported in the project materials; they have not been independently reproduced in this setup.

| Model | Hold-out accuracy | Hold-out F1 | K-fold accuracy | K-fold F1 |
|---|---:|---:|---:|---:|
| Random Forest | 0.933 | 0.928 | 0.925 | 0.922 |
| EfficientNetB0 | 0.947 | 0.943 | 0.908 | 0.904 |

## Attribution

The existing project materials identify **Muhammed Doğru** as the author. Keep this attribution when sharing or adapting the work. The dataset is provided by [Masoud Nickparvar on Kaggle](https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset). No software license file was included with the downloaded project; confirm the original source's license or get permission before publishing a public copy.
### Student contribution

Repository setup and upload: Abhishek Kashyap. This is a first-semester learning project.
