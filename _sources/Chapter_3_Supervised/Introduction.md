# Introduction

A wide number of ML techniques can be used to address the problem of fraud detection. This is directly reflected by the huge amount of published papers on the topic in the last decade. Despite this large volume of research work, most of the proposed approaches follow a common baseline ML methodology summarised in Fig. 2.

![alt text](images/baseline_ML_workflow.png)
<p style="text-align: center;">
Fig. 2. Baseline methodology followed by most of the proposed approaches in the recent surveys on the topic.  
</p>

We focus on supervised machine learning methods for rare event 
detection tasks like fraud detection, that can be broken down into two steps. 
The first step of supervised learning consists of building a prediction model 
from a set of labelled (`normal` or `fraudulent`) historical data. In the 
second step, the prediction model obtained from the supervised learning process 
is used to predict the label of new transactions.

Formally, a prediction model is a parametric function with parameters 
$\theta$ takes an input $x$ from an input space 
$\mathcal{X} \in \mathbb{R}^n$, and outputs a prediction 
$\hat{y} = p(x, \theta)$ over an output space $\mathcal{Y} \in \mathbb{R}$.

The input space $\mathcal{X}$ usually differs from the space of raw 
transaction data as most supervised learning algorithms require the input 
domain to be real-valued, and therefore may require the transformation of 
transaction features that are not real numbers (such as timestamps, 
categorical variables, etc). It may also be beneficial to perform feature 
engineering to enrich the transaction data to improve the detection 
performance.

For fraud detection, the output space $\mathcal{Y}$ is usually the predicted 
binary class for a given input $x$, that is $\mathcal{Y} = \{0, 1\}$. 
Alternatively, the output may also be expressed as a fraud probability, with 
$\mathcal{Y} = [0, 1]$, where values closer to 1 express higher probability 
of fraud.

The training of a prediction model $p(x, \theta)$ consists of finding the 
parameters $\theta$ that minimises a loss function, that compares the true 
label $y$ to the predicted label $\hat{y} = p(x, \theta)$ for an input $x$. Due 
to the high class imbalance (much more `normal` than `fraudulent` 
transactions), careful consideration must be given to the choice of loss 
function for fraud detection. Particular care must also be taken in practice 
when splitting the dataset into training and validation sets, due to the 
sequential nature of transactions.