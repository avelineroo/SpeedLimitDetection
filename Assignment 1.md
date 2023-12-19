# Assignment 1

## 1. References

a. **GTSDB**: Houben, Sebastian, et al. "Detection of traffic signs in real-world images: The German Traffic Sign Detection Benchmark." *The 2013 international joint conference on neural networks (IJCNN)*. Ieee, 2013.

b. **TT100K**: Zhu, Zhe, et al. "Traffic-sign detection and classification in the wild." *Proceedings of the IEEE conference on computer vision and pattern recognition*. 2016.

c. **Faster-RCNN**: Ren, Shaoqing, et al. "Faster r-cnn: Towards real-time object detection with region proposal networks." *Advances in neural information processing systems* 28 (2015).

d. **Traffic sign detection systems**: Arcos-García, Álvaro, Juan A. Álvarez-García, and Luis M. Soria-Morillo. "Evaluation of deep neural networks for traffic sign detection systems." *Neurocomputing* 316 (2018): 332-344.

## 2. Topic

Developement of Speed Limit Detection System for self-driving cars

## 3. Type of project

My project belongs to *Bring your own method*.

## 4. Summary

### **Idea and Approach**

Speed limits signs play a crucial role in road safety by informing drivers about the allowed speed in a particular area. However, existing research predominantly focuses on the classification of major categories of traffic signs, such as prohibitory, mandatory, and danger signs [[1](https://www.sciencedirect.com/science/article/pii/S092523121830924X)]. There is a lack of specific studies on speed limit sign detection. Therefore, my project aims to address this gap by developing a speed limit sign detection system using the state-of-the-art Faster-RCNN model.

### **Dataset**

To train the Faster-RCNN model for speed limit detection task, this project will utilize one or more commonly used datasets for traffic sign detection, such as German Traffic Sign Recognition Benchmark (GTSRB) Dataset or Tencent-Tsinghua 100K Dataset. The applicable dataset will be selected based on its suitability for speed limit sign detection. Pre-processing techniques will be employed to ensure the dataset is tailored specifically for speed limit sign detection task.

### **Plan**

1. **Data preparation**: 
   1. Read papers on the datasets: 1 day
   2. Conduct Exploratory Data Analysis: 4 hours
   3. Select relevant data: 2 hours

2. **Designing and building an appropriate network**:

   1. Read Faster-RCNN paper: 3 days
   2. Learn the implementation of Faster-RCNN model: 2 days
   3. Implement data preprocessing and augmentation techniques: 2 days

3. **Training and fine-tuning the model**:

   1. Train the model using the training dataset: 2 day
   2. Evaluate and fine-tune the model perforamance based on validation results: 2 day
   3. Optimize model hyper parameters: 2 day

4. **Building an application to present the results**:

   1. Learning the required libraries for development of the application: 1 day
   2. Develop the application layout and user interface: 1 day
   3. Integrate the trained model into the application: 1 day
   4. Test and debug the application: 2 day

5. **Writing the final report**: 5 days

6. **Preparing the presentation**: 3 days

   



