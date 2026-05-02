# Detection and Classification of Fetal Brain Abnormalities Using Ultrasound Images

This project focuses on the detection and classification of fetal brain abnormalities from ultrasound images using deep learning techniques. The goal is to support early prenatal screening by identifying whether a fetal brain ultrasound image is normal or abnormal, and further classifying abnormal cases into specific abnormality categories.

The system uses a combination of object detection and image classification models, including **YOLOv8** for binary and multi-class detection, and a **Fine-Tuned AlexNet** model for multi-class classification. A Streamlit-based interface is also included to make the system easier to use for image upload and prediction.

---

## Project Overview

Fetal brain abnormalities can have serious implications for fetal development and postnatal health. Early detection is important because it can help healthcare professionals and expectant families make informed clinical decisions, plan treatment, and prepare for postnatal care.

This project applies deep learning to fetal brain ultrasound images to perform three main tasks:

1. **Binary Detection**
   - Detects whether an ultrasound image is normal or abnormal.
   - Implemented using YOLOv8.

2. **Multi-Class Detection**
   - Detects and localizes specific fetal brain abnormalities using bounding boxes.
   - Implemented using YOLOv8.

3. **Multi-Class Classification**
   - Classifies an ultrasound image into one of several fetal brain abnormality categories.
   - Implemented using a Fine-Tuned AlexNet model.

---

## Objectives

The main objectives of this project are:

- To detect fetal brain abnormalities from ultrasound images.
- To classify abnormal ultrasound images into specific abnormality categories.
- To compare AI-based predictions with human expert assessment.
- To build an interactive Streamlit application for real-time image prediction.
- To evaluate model performance using standard metrics such as precision, recall, F1-score, accuracy, and mAP.

---

## Dataset

The dataset consists of fetal brain ultrasound images categorized into normal and abnormal cases. The abnormal cases are further divided into multiple fetal brain abnormality classes.

The abnormality categories include:

- Arnold-Chiari Malformation
- Arachnoid Cyst
- Cerebellar Hypoplasia
- Colpocephaly
- Encephalocele
- Intracranial Hemorrhage
- M-Magna
- Mild Ventriculomegaly
- Moderate Ventriculomegaly
- Polencephaly
- Severe Ventriculomegaly

The dataset was curated from multiple sources and annotated for detection and classification tasks.

---

## System Workflow

The overall workflow of the project is:

1. Collect fetal brain ultrasound images.
2. Preprocess images by resizing, normalizing, and enhancing image quality.
3. Apply data augmentation techniques such as:
   - Horizontal flipping
   - Vertical flipping
   - Rotation
   - Brightness adjustment
4. Train YOLOv8 for binary abnormality detection.
5. Train YOLOv8 for multi-class abnormality detection and localization.
6. Train a Fine-Tuned AlexNet model for multi-class image classification.
7. Evaluate all models using appropriate performance metrics.
8. Deploy the models through a Streamlit web application.

---

## Models Used

### YOLOv8

YOLOv8 was used for object detection tasks. It was applied in two stages:

- **Binary Detection:** Normal vs Abnormal
- **Multi-Class Detection:** Detection and localization of specific fetal brain abnormalities

YOLOv8 was selected because of its strong object detection performance, speed, and ability to localize abnormalities using bounding boxes.

### Fine-Tuned AlexNet

AlexNet was used for multi-class image classification. The architecture was fine-tuned for fetal brain ultrasound images by modifying the network for the specific number of abnormality classes in the dataset.

The model classifies the complete ultrasound image into one of the predefined fetal brain abnormality categories.

---

## Tools and Technologies

The project uses the following tools and technologies:

- Python
- YOLOv8
- AlexNet
- TensorFlow / Keras
- PyTorch
- OpenCV
- Roboflow
- Streamlit
- NumPy
- Pandas
- Matplotlib
- Scikit-learn

---

## Results

### Binary Detection Using YOLOv8

The YOLOv8 model achieved strong performance for binary detection of fetal brain abnormalities.

| Metric | Value |
|---|---:|
| Precision | 0.984 |
| Recall | 0.973 |
| mAP@0.5 | 0.988 |
| mAP@0.5:0.95 | 0.782 |

The model showed strong ability to distinguish between normal and abnormal fetal brain ultrasound images.

---

### Human Expert Comparison

The model predictions were compared with assessments from a medical expert, Dr. Rahul Nijhara.

| Evaluator | Accuracy |
|---|---:|
| Human Expert Assessment | 80% |

This comparison highlights the potential of AI-based systems to support medical experts by providing consistent and objective predictions.

---

### Multi-Class Detection Using YOLOv8

The YOLOv8 model was also trained for multi-class abnormality detection.

| Metric | Value |
|---|---:|
| Precision | 0.986 |
| Recall | 0.857 |
| mAP@0.5 | 0.955 |
| mAP@0.5:0.95 | 0.642 |

The results show that YOLOv8 can effectively identify and localize multiple fetal brain abnormality classes.

---

### Multi-Class Classification Using Fine-Tuned AlexNet

The Fine-Tuned AlexNet model was used for multi-class classification of ultrasound images.

| Metric | Value |
|---|---:|
| Test Accuracy | 93.83% |
| Macro Average F1-Score | 0.9375 |
| Weighted Average F1-Score | 0.9389 |

The model achieved strong classification performance across the predefined abnormality classes.

---

## Overall Performance Summary

| Model | Task | Performance Metric | Value |
|---|---|---|---:|
| YOLOv8 | Binary Detection | mAP@0.5 | 0.988 |
| YOLOv8 | Multi-Class Detection | mAP@0.5 | 0.955 |
| Fine-Tuned AlexNet | Multi-Class Classification | Test Accuracy | 93.83% |

---

## Streamlit Application

The project includes a Streamlit-based graphical user interface that allows users to upload fetal brain ultrasound images and receive model predictions.

The interface supports:

- Image upload
- Confidence threshold adjustment
- Detection result visualization
- Bounding box display for detected abnormalities
- Multi-class classification output

To run the Streamlit app:

```bash
streamlit run app.py