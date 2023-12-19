# SpeedLimitDetection
## Overview
This repository contains the implementation for developing a speed limit sign detection system using the classic Faster-RCNN model.

Speed limits signs play a crucial role in road safety by informing drivers about the allowed speed in a particular area. However, existing research predominantly focuses on the classification of major categories of traffic signs, such as prohibitory, mandatory, and danger signs [[1](https://www.sciencedirect.com/science/article/pii/S092523121830924X)]. There is a lack of specific studies on speed limit sign detection. Therefore, my project aims to address this gap by developing a speed limit sign detection system using the state-of-the-art Faster-RCNN model.

## Model Architecture
- **Model Type:** Faster-RCNN
- **Backbone Typ:e** ResNet
- **Backbone Depth:** 50 layers
- **Framework:** Detectron2

## Dataset
- combination of two traffic signs dataset [Tencent-Tsinghua100K](https://cg.cs.tsinghua.edu.cn/traffic-sign/) and [GTSDB](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&cad=rja&uact=8&ved=2ahUKEwiyiZjHsZyDAxVf8rsIHTw8A_EQFnoECA0QAQ&url=https%3A%2F%2Fbenchmark.ini.rub.de%2F&usg=AOvVaw3ydXAIMKQ2BxWRtbpCBe9c&opi=89978449)
- selection of samples related to speed limit signs

## Requirements
```
pip install -r requirements.txt
```
In addition, install detectron2 following [here](https://detectron2.readthedocs.io/en/latest/tutorials/install.html).

## Usage
- `data_preparation.ipynb`: notebook for explatory data analysis, dataset combination and exportation.
- `training.ipynb`: notebook for data loading, model training and evaluation in Detectron2

## Summary of Object Detector Performance

#### Error Metric

I choose **Average Precision (AP)** as the error metric for my model. AP is a widely used metric in the context of object detection, and it provides a way to quantify the accuracy of the object detector across different IoU thresholds and different object sizes. 

- **Overall Average Precision (AP):** the average precision at different Intersection over Union (IoU) thresholds, ranging from 0.5 to 0.95 in steps of 0.05. This metric effectively measures the model's accuracy across various overlap thresholds between the predicted and actual bounding boxes.
- **AP50:** AP at 50% IoU threshold
- **AP75:** AP at 75% IoU threshold
- **APs:** Average Precision for small objects
- **APm:** Average Precision for medium-sized objects
- **APl:** Average Precision for large objects

#### Target and Achieved Value of Error Metrics:

**Target:** AP of 70~80% could guarantee decent model performance

**Achieved performance**

|   AP   |  AP50  |  AP75  |  APs   |  APm   |  APl   |
| :----: | :----: | :----: | :----: | :----: | :----: |
| 49.250 | 66.192 | 57.629 | 38.403 | 57.494 | 64.188 |

Per-category bbox AP:

| category |   AP   | category |   AP   | category |   AP   |
| :------: | :----: | :------: | :----: | :------: | :----: |
|  pl100   | 67.376 |  pl120   | 54.484 |   pl20   | 23.172 |
|   pl30   | 37.677 |   pl40   | 53.247 |   pl50   | 50.332 |
|   pl60   | 45.850 |   pl70   | 55.378 |   pl80   | 55.734 |

# Preliminary Analysis

1. Regarding Overall Average Precision, the AP of 49.25% is the average precision at different IoU thresholds (typically from 0.5 to 0.95 with a step size of 0.05). Notably, this performance metric aligns closely with the AP observed during training, as indicated by the training AP curve. This consistency between training and validation sets suggests that the model is not significantly overfitting. However, this performance might not be perfect, there is potential for further refinement to enhance its precision. In terms of AP50 and AP75, the values of 66% and 57%, respectively, highlight the model's robust performance at 50% and 75% IoU thresholds. 

2. When evaluating performance based on object sizes, the model exhibits a remarkable precision in detecting large objects. This suggests a potential area of focus for model improvement might be enhancing its ability to accurately identify smaller objects.

3. The Per-category AP varies significantly across categories (e.g., 67.376 for pl100 and 23.172 for pl20). Given that the pl100 has the most samples while pl20 has the least samples, this variation is probably due to the amount of the data. 

   To address this imbalance and improve model performance on underrepresented categories like pl20, I believe implementing data augmentation strategies during retraining on this baseline model could be an effective approach. By enriching the dataset, especially for categories with fewer samples, the model may develop a more balanced and robust understanding of all categories, thereby improving its overall precision.

   

# Time Spent and Work Breakdown:

| Task Phase                      | Description                                                  | Time Spent (Approx.) |
| ------------------------------- | ------------------------------------------------------------ | -------------------- |
| Data Preparation                | Preparing GTSDB, EDA on GTSDB, preparing TT100K, EDA on TT100K, combination of the two datasets, convert dataset annotations to COCO format | 8 hours              |
| Learning Object Detection Algos | Studying Faster-RCNN model and its predecessors              | 12 hours             |
| Learning to Use Detectron2      | Gaining proficiency in using the Detectron2 framework for trainig object detection models | 6 hours              |
| Model Training and Evaluation   | Training of the model, model evaluation, and analysis        | 8 hours              |


