# Early Detection of Alzheimer's Using Convolutional Neural Networks for MRI Scan Classification

This repository contains the code and documentation for the ANA 699 thesis project:  
**Early Detection of Alzheimer's Using Convolutional Neural Networks for MRI Scan Classification**  
Team Members: Leticia Genao, Brashon Ford, Misato Nasu, Kevin Carrillo

---

## Project Overview
This project focuses on classifying Alzheimer’s severity levels from MRI images using machine learning models. Multiple datasets were loaded, combined, preprocessed, and used to train both a Convolutional Neural Network (CNN) and a baseline Support Vector Machine (SVM) model.

The workflow includes:
- Mounting Google Drive for dataset access  
- Loading and preprocessing MRI images  
- Combining two separate MRI datasets  
- Building and training a CNN model  
- Evaluating model performance  
- Training and evaluating an SVM model as a baseline comparison  

---

## Datasets
Images were loaded from the following datasets stored in Google Drive:

- Alzheimer’s Imaging Dataset  
  - NonDemented  
  - VeryMildDemented  
  - MildDemented  
  - ModerateDemented  

- OASIS Subset  
  - Non Demented  
  - Very mild Dementia  
  - Mild Dementia  
  - Moderate Dementia  

Class mapping for both datasets was aligned using numeric labels (0–3).

After combining:
- **Total images:** 14,609  
- **Class distribution:**  
  - Very Mild Demented: 4,792  
  - Moderate Demented: 540  
  - Mild Demented: 3,717  
  - Non Demented: 5,560  

---

## Preprocessing
- Images resized to **128×128×3**  
- Pixel values normalized to \[0, 1\]  
- Labels one-hot encoded  
- Datasets shuffled and split into training/testing sets (80/20)

---

## CNN Model
A Sequential CNN model was built with the following layers:

- Conv2D → MaxPooling  
- Conv2D → MaxPooling  
- Conv2D → MaxPooling  
- Flatten  
- Dense(128) + Dropout(0.5)  
- Dense(4) with softmax activation  

The model was compiled with:
- Optimizer: Adam  
- Loss: categorical crossentropy  
- Metrics: accuracy  

Training used early stopping to prevent overfitting.

### CNN Results
The CNN achieved:
- **Accuracy:** 0.99  
- Very high precision, recall, and F1-scores across all four classes  
- Strong convergence shown in training/validation loss and accuracy curves  
- A clear confusion matrix demonstrating high classification performance  

---

## SVM Model
For comparison, an SVM model was trained using flattened and standardized images.

### SVM Results
- **Accuracy:** 0.97  
- Strong macro-average and weighted-average metrics  
- Confusion matrix indicates generally reliable performance, though lower than the CNN  

---

## Files Included
- **EDA.ipynb** — Contains dataset loading, exploration, and preprocessing steps.  
- **Alzheimer’s Detection and Severity Classification by MRI Analysis.pdf** — Full project write-up including background, methods, model evaluation, and interpretation.

---

## Notes
- This README summarizes the code and workflow provided in the project.  
- Additional notebooks (such as model training notebooks) can be added later if needed.  
