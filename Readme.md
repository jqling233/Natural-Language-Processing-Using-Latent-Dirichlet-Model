# Natural Language Processing
[Latent Dirichlet Model Notebook](https://github.com/QiangWANGWQ/Natural-Language-Processing-Using-Latent-Dirichlet-Model/blob/master/Topic_Analysis_FAA.ipynb)

## Abstract

This program establishes an approach to extract knowledge from structured open-source data, with a focus on natural language processing and text analytics. Our analysis consists of two components: first, best practice for topic modeling, and then, interpretation of statistical results in aviation context. In order to extract knowledge from narratives in our dataset, we utilized several packages in python to break down sentences into words and identify topics which frequently shows up. After initial exploration, a list of stop words, which refers to topics that are not relevant to aviation safety, was excluded from our topics. And iterations take place a few times until we conclude a model that comes with the best possible outcomes: 20 topics that represents 20 frequent problems in aviation safety fields.

![MacDown Screenshot](https://github.com/QiangWANGWQ/Machine_Learning_Project/blob/master/pics/cactus.jpg)

## Introduction
Organizations collect safety reporting data across a variety of domains in transportation to help inform analysis to improve safety. Hitherto, data size of the safety report experienced a rapid growth and format of the report became more complex to be analyzed. While various tools are available now for us to deal with big data, a key challenge in utilizing these safety reports is to extract information from text narratives within the dataset. The extracted information can help safety related studies or further downstream analysis. To make the best use of these safety reports, we develop a Natural Language Processing based approach that automatically extract and tag information in safety narratives.

### Files


**train/** - the training set images

**test/** - the test set images (you must predict the labels of these)

**train.csv** - the training set labels, indicates whether the image has a cactus (has_cactus = 1)

**sample_submission.csv** - a sample submission file in the correct format

## Notebook Topics
* **Data Description**

The **train** dataset has 17500 rows and 2 columns.
The **test** dataset has 4000 rows and 2 columns.

* **Image in Dataset**

![MacDown Screenshot](https://github.com/QiangWANGWQ/Machine_Learning_Project/blob/master/pics/Screen%20Shot%202019-06-28%20at%206.15.11%20PM.png)

* **Import Image to Data type**

(Quoted from Shahules786's kernel: 'Getting started with CNN and VGG16')

1. Read the picture files
2. Decode JPEG content to RGB pixels
3. Convert this into floating tensors
4. Rescale pixel values (between 0 to 255) to [0,1] interval.

* **Build Convolutional Neural Network Model (with Keras)**


Try different parameters

1. RMSPROP
2. ADAM
3. SGD
4. Adamax
5. Adagrad
6. Adadelta
7. Nadam

* Kaggle Score 

In sum, 'adam' is the best optimizer and 'sgd' is the worst, the highest overall score of the competition is 0.9966.
