(Metrics)=
# Choosing the right metric

Selecting an evaluation metric is an important step in any project. 
Choosing the wrong metric can mean choosing a model that solves a different 
problem from the problem we actually want solved.

The metric must capture those characteristics about a model and its 
predictions that are most important to the project stakeholders. This 
is challenging, as there are many metrics to choose from and often project 
stakeholders are not sure what they want. Based on whether the positive 
(minority) class is more important, we make the following recommendations 
for choosing a metric; 

1. **Positive class is more important**
    * If both false positives and false negatives are equally important, 
        then use the area under the precision recall curve (PR AUC). This 
        maximises both precision and recall over all possible thresholds.
    * If false negatives are more costly, then use the F(2) measure. 
    * If false positives are more costly, then use the F(0.5) measure.
2. **Both classes are equally important**
    * Use the area under the ROC curve (ROC AUC). This maximises the 
        true positive rate and minimises the false positive rate over all 
        possible thresholds.
where the F($\beta$) measure is defined as
\begin{gather*}
  F(\beta) = \frac{(1 + \beta^2)*\text{precision}*\text{recall}}{\beta^2*\text{precision}*\text{recall}} \, .
\end{gather*}

Tables 1 and 2 present the performance metrics of the machine 
learning algorithms, logistic regression {cite}`kleinbaum2002logistic` and bagged 
descision tree {cite}`breiman1996bagging`, for the fraud classification task both 
before and after using SMOTE to balance the classes. We use the first 14 days of 
transactions to train the models and the subsequent 14 days are used for evaluation. 
Based on these results it appears that class balancing using SMOTE does not provide 
a significant advantage in classifying fraudulent transactions in this dataset.