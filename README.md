# Traffic_Signal_Recognition

### Abstract


Traffic signs are designed to be easily characterized by drivers to convey clear and concise information in real-world situations. The visual appearance can vary widely depending on weather conditions or partial occlusions, and while a human brain can often fill in missing information, a machine requires training. In practice, a driver, whether human or machine, needs to be able to classify road signs with an extremely high degree of accuracy. However, these machines have been designed to be easily recognizable by humans, while computers interpreting them remains to be solved.


To test the performance of modern machine learning algorithms, we obtained a publicly available data set of over 50,000 road signs in Germany, each belonging to one of 43 classes. The data was considered in the second stage of the German Traffic Sign Recognition Benchmark held at IJCNN 2011. We tested a number of models on Python and found that CNNs are especially effective at discerning the signs.


### Introduction


Have you wondered that at some point in your life you’ll own a self driving car? If you’re under 70, we hope you answered yes.


The reality is whether we like it or not that self-driving cars are the future. Even if we’re not there yet, the technology is growing as cars become more autonomous and less dependent on drivers. In order for them to become fully autonomous, they will need to be able to take in and process information more quickly than the human eye and brain can, and accurately be able to make driving decisions. An important component of this is reading and interpreting road signs, which is what we’ve decided to focus our project on.


This is the goal of the project: creating a classifier that can quickly and accurately classify traffic signs. No autonomous car would be complete without such a classifier, so we aimed to develop one with the idea of a widespread application in mind.


### Dataset


A dataset of 43 classes of road signs with 51,840 images in Germany was gathered (https://www.kaggle.com/meowmeowmeowmeowmeow/gtsrb-german-traffic-sign). The classes included stop signs, speed limits, yields, road work, and similar traffic signs. Pretty much everything one would see on a road aside from street names and mileage markers. Each image was converted into an array using the PIL module on Python to perform the analysis.

### Exploring New Datasets


Post training three models on the original 43-feature dataset, a further exploration of the models was done using a new dataset (https://www.kaggle.com/aadilmalik94/trafficsigns). A new 62-feature dataset was used to train the CNNs. Three CNNs were trained, with the 3-layered model giving the best test accuracy. The individual models are looked at in-depth below.

### Validation Using External Data


The trained CNNs were tested using external data that was not part of the 2 datasets through which the models were trained. This external data, or traffic sign images, was obtained through Google. Since these images were not preprocessed for classification using the models, this exercise helped test the robustness of the models on real-world data with no preprocessing.

### Results & Inference


1. Model Accuracy
- Solution with 2-layered network performed better with original dataset, suggesting overfitting in complex models
- Given less data points, model with higher complexity performs better, but this might also be due to erroneous pattern recognitions as even higher complexity model with this data didn’t do well on the external Google Images
- Both grayscale and colored images led to almost similar accuracy, which might hint that more information or features doesn’t aid in getting better prediction here


2. Individual Class Accuracy & Misclassifications
- Classes with more data points have better prediction accuracy
- Reasons for misclassification include similarity between signs (like speed limit signs) and quality (dark images with poor lighting & blurred images : resizing images affects quality)
