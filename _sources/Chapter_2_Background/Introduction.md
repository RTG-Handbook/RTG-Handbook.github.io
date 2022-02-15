# Introduction

Many real world applications require the detection of anomalies in large 
data. For example, intrusions in computer networks {cite}`bhuyan2013network`, 
fraudulent transactions in financial data {cite}`fiore2019using`, system 
failures {cite}`ribeiro2016sequential` and road accidents in traffic data 
{cite}`theofilatos2016predicting` are significant but rare events that require 
detection. In the literature, such anomalies may be referred to as 
abnormalities, novelties, outliers, exceptions, aberrations or 
contaminations, among others.

Anomaly detection is recognised as a very challenging problem. It has 
become infeasible for investigators to manually detect anomalies in 
real world applications, due to the large number of observations and high 
dimensionality. As a result, the use of machine learning techniques is 
becoming increasingly popular since they offer an effective and scalable 
solution to automate the process of identifying anomalies from 
large volumes of data. However, due to the inherent imbalance of the classes 
in such datasets, statistical methods tend to underestimate the probability 
of anomalies and perform poorly {cite}`king2001logistic`.

We present techniques that build towards a general framework 
for employing machine learning based models for anomaly detection. Based on the 
availability of class labels (`normal` or `anomaly`), machine learning 
algorithms for anomaly detection can be broadly classified into,

1. **Supervised methods**: Supervised machine learning algorithms like Logistic regression, Random forests, 
Gradient Boosting Machines, and Neural Networks require a data set that has records 
labelled as `normal` or `anomaly` and involves training a classifier. The key 
difference to typical statistical classification problems is the inherent imbalance 
in the number of instances of anomalous events compared to normal ones.
2. **Unsupervised methods**: Unsupervised machine learning algorithms like Local 
Outlier Factor, one-class SVM, 
and Isolation Forests detect outliers in an unlabelled data set under the assumption 
that the majority of the instances in the data set are normal by looking for instances 
that seem to fit least to the remainder of the data set. They can be used to find 
abnormal patterns of a user/system behaviour in order to detect anomalies.