# Natural Language Processing
[Latent Dirichlet Model Notebook](https://github.com/QiangWANGWQ/Natural-Language-Processing-Using-Latent-Dirichlet-Model/blob/master/Topic_Analysis_FAA.ipynb)

## Abstract

This program establishes an approach to extract knowledge from structured open-source data, with a focus on natural language processing and text analytics. Our analysis consists of two components: first, best practice for topic modeling, and then, interpretation of statistical results in aviation context. In order to extract knowledge from narratives in our dataset, we utilized several packages in python to break down sentences into words and identify topics which frequently shows up. After initial exploration, a list of stop words, which refers to topics that are not relevant to aviation safety, was excluded from our topics. And iterations take place a few times until we conclude a model that comes with the best possible outcomes: 20 topics that represents 20 frequent problems in aviation safety fields.

![MacDown Screenshot](https://github.com/QiangWANGWQ/Machine_Learning_Project/blob/master/pics/cactus.jpg)

## Introduction
Organizations collect safety reporting data across a variety of domains in transportation to help inform analysis to improve safety. Hitherto, data size of the safety report experienced a rapid growth and format of the report became more complex to be analyzed. While various tools are available now for us to deal with big data, a key challenge in utilizing these safety reports is to extract information from text narratives within the dataset. The extracted information can help safety related studies or further downstream analysis. To make the best use of these safety reports, we develop a Natural Language Processing based approach that automatically extract and tag information in safety narratives.

## Latent Dirichlet Model
The plot summarizes the key idea behind Latent Dirichlet Allocation model. Parameter (<a href="https://www.codecogs.com/eqnedit.php?latex=\alpha" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\alpha" title="\alpha" /></a>)
 determine the Dirichlet distribution Dir (<a href="https://www.codecogs.com/eqnedit.php?latex=\alpha" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\alpha" title="\alpha" /></a>) (The dimension is the number of topics) from which the topic multinomial distribution v:<a href="https://www.codecogs.com/eqnedit.php?latex=p(z_{n}|\theta)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?p(z_{n}|\theta)" title="p(z_{n}|\theta)" /></a>  of each document is sampled from. And for the inner layer, the topic assigned for each word is sampled from the multinomial topic distribution <a href="https://www.codecogs.com/eqnedit.php?latex=v" target="_blank"><img src="https://latex.codecogs.com/gif.latex?v" title="v" /></a>. Given the topic <a href="https://www.codecogs.com/eqnedit.php?latex=z" target="_blank"><img src="https://latex.codecogs.com/gif.latex?z" title="z" /></a> for the word, the word is sampled from the multinomial distribution <a href="https://www.codecogs.com/eqnedit.php?latex=\varphi&space;\:&space;\(p(w_{n}|z_{n}\beta)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\varphi&space;\:&space;\(p(w_{n}|z_{n}\beta)" title="\varphi \: \(p(w_{n}|z_{n}\beta)" /></a>. But for this multinomial distribution <a href="https://www.codecogs.com/eqnedit.php?latex=\varphi&space;:\(p(w_{n}|z_{n}\beta)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\varphi&space;:\(p(w_{n}|z_{n}\beta)" title="\varphi :\(p(w_{n}|z_{n}\beta)" /></a>, it’s sampled from the Dir(\<a href="https://www.codecogs.com/eqnedit.php?latex=\beta" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\beta" title="\beta" /></a>) (The dimension is the number of words). So there are three hierarchies in the sampling model. The parameters for the two Dirichlet parameters \(\alpha \) and \(<a href="https://www.codecogs.com/eqnedit.php?latex=\beta" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\beta" title="\beta" /></a>) are fixed for all documents. For each document, the vector parameters <a href="https://www.codecogs.com/eqnedit.php?latex=\theta" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\theta" title="\theta" /></a>) for the multinomial distribution \(v\) of topic distribution given each document is sampled from the Dirichlet distribution whose dimension is the total number of topics. For each word, the topic assigned for it is sampled from multinomial distribution \(v\) and the word likelihood is sampled from the Dirichlet parameters whose dimension is the total number of words and parameter is <a href="https://www.codecogs.com/eqnedit.php?latex=\beta" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\beta" title="\beta" /></a>.


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
