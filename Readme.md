# Natural Language Processing
[Latent Dirichlet Model Notebook](https://github.com/QiangWANGWQ/Natural-Language-Processing-Using-Latent-Dirichlet-Model/blob/master/Topic_Analysis_FAA.ipynb)

## Introduction

This program establishes an approach to extract knowledge from structured open-source data, with a focus on natural language processing and text analytics. Our analysis consists of two components: first, best practice for topic modeling, and then, interpretation of statistical results in aviation context. In order to extract knowledge from narratives in our dataset, we utilized several packages in python to break down sentences into words and identify topics which frequently shows up. After initial exploration, a list of stop words, which refers to topics that are not relevant to aviation safety, was excluded from our topics. And iterations take place a few times until we conclude a model that comes with the best possible outcomes: 20 topics that represents 20 frequent problems in aviation safety fields.

![MacDown Screenshot](https://github.com/QiangWANGWQ/Machine_Learning_Project/blob/master/pics/nlp_(1).png)

Organizations collect safety reporting data across a variety of domains in transportation to help inform analysis to improve safety. Hitherto, data size of the safety report experienced a rapid growth and format of the report became more complex to be analyzed. While various tools are available now for us to deal with big data, a key challenge in utilizing these safety reports is to extract information from text narratives within the dataset. The extracted information can help safety related studies or further downstream analysis. To make the best use of these safety reports, we develop a Natural Language Processing based approach that automatically extract and tag information in safety narratives.

## Latent Dirichlet Model
The plot summarizes the key idea behind Latent Dirichlet Allocation model. Parameter <a href="https://www.codecogs.com/eqnedit.php?latex=\alpha" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\alpha" title="\alpha" /></a>
 determines the Dirichlet distribution Dir (<a href="https://www.codecogs.com/eqnedit.php?latex=\alpha" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\alpha" title="\alpha" /></a>) (The dimension is the number of topics) from which the topic multinomial distribution v:<a href="https://www.codecogs.com/eqnedit.php?latex=p(z_{n}|\theta)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?p(z_{n}|\theta)" title="p(z_{n}|\theta)" /></a>  of each document is sampled from. And for the inner layer, the topic assigned for each word is sampled from the multinomial topic distribution <a href="https://www.codecogs.com/eqnedit.php?latex=v" target="_blank"><img src="https://latex.codecogs.com/gif.latex?v" title="v" /></a>. Given the topic <a href="https://www.codecogs.com/eqnedit.php?latex=z" target="_blank"><img src="https://latex.codecogs.com/gif.latex?z" title="z" /></a> for the word, the word is sampled from the multinomial distribution <a href="https://www.codecogs.com/eqnedit.php?latex=\varphi&space;\:&space;\(p(w_{n}|z_{n}\beta)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\varphi&space;\:&space;\(p(w_{n}|z_{n}\beta)" title="\varphi \: \(p(w_{n}|z_{n}\beta)" /></a>. But for this multinomial distribution <a href="https://www.codecogs.com/eqnedit.php?latex=\varphi&space;:\(p(w_{n}|z_{n}\beta)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\varphi&space;:\(p(w_{n}|z_{n}\beta)" title="\varphi :\(p(w_{n}|z_{n}\beta)" /></a>, it’s sampled from the Dir(<a href="https://www.codecogs.com/eqnedit.php?latex=\beta" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\beta" title="\beta" /></a>) (The dimension is the number of words). So there are three hierarchies in the sampling model. The parameters for the two Dirichlet parameters <a href="https://www.codecogs.com/eqnedit.php?latex=\alpha" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\alpha" title="\alpha" /></a> and <a href="https://www.codecogs.com/eqnedit.php?latex=\beta" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\beta" title="\beta" /></a> are fixed for all documents. For each document, the vector parameters <a href="https://www.codecogs.com/eqnedit.php?latex=\theta" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\theta" title="\theta" /></a> for the multinomial distribution v of topic distribution given each document is sampled from the Dirichlet distribution whose dimension is the total number of topics. For each word, the topic assigned for it is sampled from multinomial distribution v and the word likelihood is sampled from the Dirichlet parameters whose dimension is the total number of words and parameter is <a href="https://www.codecogs.com/eqnedit.php?latex=\beta" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\beta" title="\beta" /></a>.


## Dataset
In this project, the Service Difficulty Reports (SDR) data contains information related to aviation incidentscollected by Federal Aviation Administration (FAA), an organization operated by U.S. Depart-ment of Transportation. Records in SDR come mainly from certificate holders and certificatedrepair stations.  FAA collects this data for the purpose of planning, directing, controlling andevaluating certain assigned safety-related programs in order to improve aviation safety.Service Difficulty Reports is ideal for us to analyze topic trend of the report over the yearsto help FAA to achieve global harmonization of aviation systems for five reasons.  
* The data source is reliable.  Records were submitted and collected by authorized group whichwe mentioned before.  
* Yearly distribution of the records is stable.  We would like toknow main incident topics happened in recent years, so we focus on data from 2010 to 2019.The records in 2010 to 2018 distributed between 50,000 to 80,000, while the data in 2019 isstill collecting. 
* This dataset offers enough records for us to analyze. It contains more than500,000 rows and 80 columns. 
* It contains abundant features like aircraft model,defective parts and incident reports, so that we can analyze it from various aspects. 

we would like to present some business advice to the stakeholders in the aviation industry,so the ideal dataset should not only contain military or unscheduled plane.  While this datasetrecords data related to commercial aircraft which makes our intention possible.By identifying trends of topics in aviation safety reports over the years, our research couldpromote the changes in the aviation industry.  Based on the changes of topics, our goal was toprovide a further analysis of effective improvements and potential risk
