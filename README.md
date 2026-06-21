# Mole Risk Classification Using Deep Learning

## Overview

This project implements a deep learning-based image classification system for categorizing skin mole images into three risk levels:

* **Low Risk**
* **Medium Risk**
* **High Risk**

The model is trained using TensorFlow and Keras and learns visual patterns from labeled mole images. After training, it can predict the risk category of new images placed in the test folder.

---

## Project Objectives

The main objectives of this project are:

1. To build an image classification model capable of distinguishing between different mole risk levels.
2. To explore the application of Convolutional Neural Networks (CNNs) in medical image analysis.
3. To evaluate the effectiveness of deep learning techniques on a small image dataset.
4. To provide an educational demonstration of machine learning for skin lesion classification.

---

## Dataset Structure

The dataset is organized as follows:

```text
lab2_moles/
│
├── train/
│   ├── low/
│   ├── medium/
│   └── high/
│
└── test/
```

### Training Folders

* `train/low` → Low-risk mole images
* `train/medium` → Medium-risk mole images
* `train/high` → High-risk mole images

### Test Folder

The `test` folder contains images that will be classified by the trained model.

---

## Technologies Used

* Python
* TensorFlow
* Keras
* NumPy
* Matplotlib
* Google Colab

---

## Methodology

### 1. Data Loading

Images are automatically loaded from the training folders using TensorFlow's `image_dataset_from_directory()` function.

### 2. Data Preprocessing

The following preprocessing steps are applied:

* Image resizing to 224 × 224 pixels
* Pixel value normalization
* Dataset shuffling
* Batch generation

### 3. Data Augmentation

To improve generalization and reduce overfitting, the following augmentation techniques are used:

* Horizontal flipping
* Rotation
* Zooming
* Contrast adjustment

### 4. CNN Architecture

The model consists of:

* Input Layer
* Rescaling Layer
* Convolutional Layers
* Max Pooling Layers
* Dropout Layers
* Dense Fully Connected Layers
* Output Classification Layer

### 5. Training

The model is trained using:

* Adam Optimizer
* Sparse Categorical Crossentropy Loss
* Accuracy Metric

### 6. Prediction

After training, the model predicts the risk level of images located in the test directory and displays:

* Predicted class
* Confidence score
* Test image visualization

---

## Running the Project

### Step 1: Mount Google Drive

```python
from google.colab import drive
drive.mount('/content/drive')
```

### Step 2: Verify Dataset Structure

Ensure that the dataset folders match the expected structure.

### Step 3: Run the Training Cell

Execute the training code to build and train the CNN model.

### Step 4: Run Predictions

Place test images in:

```text
lab2_moles/test/
```

The model will automatically classify all supported images found in the folder.

---

## Example Output

```text
Image: sample_mole.jpg

Class probabilities:
high: 12.4%
low: 81.7%
medium: 5.9%

Final prediction: low
Confidence: 81.7%
```

---

## Results

The model successfully learns visual features from the provided dataset and can classify unseen mole images into one of the three risk categories.

Training and validation accuracy/loss graphs are generated to monitor learning performance and identify potential overfitting.

---

## Limitations

This project was developed using a relatively small dataset.

Deep learning models typically require large and diverse datasets to achieve high accuracy and strong generalization. With limited training samples, the model may struggle to correctly classify previously unseen images and may be sensitive to:

* Lighting conditions
* Image quality
* Camera differences
* Class imbalance
* Similar visual characteristics between categories

Therefore, the predictions produced by this system should be considered experimental and educational rather than medical diagnoses.

---

## Future Improvements

Potential enhancements include:

* Collecting a larger dataset
* Improving class balance
* Applying transfer learning using pretrained models such as MobileNet, EfficientNet, or ResNet
* Implementing cross-validation
* Adding more advanced image preprocessing techniques
* Evaluating additional performance metrics such as precision, recall, and F1-score

---

## Disclaimer

This project is intended solely for educational and research purposes. It is not a medical device and should not be used for clinical diagnosis or healthcare decision-making. Any concerns regarding skin lesions should be evaluated by qualified healthcare professionals.

---

## Author

Developed as part of a machine learning and image classification project using TensorFlow and Keras.
