(Exploratory_Data_Analysis)=
# Exploratory Data Analysis

To illustrate the methodology developed as part of our work, we use a 
public dataset containing Vesta's real world e-commerce transactions made 
available as part of the Kaggle competition 
`IEEE-CIS Fraud Detection: Can you detect fraud from customer transactions?`
{cite}`kaggle2020data`. Financial fraud detection is a typical example 
of rare event detection where the data is often characterised by large number of 
samples and a severe imbalance in the number fraudulent samples compared to normal
ones.

The original dataset contains over 400 variables, though the vast majority 
of the variables have their names and values masked for privacy protection. 
We exclude the masked variables, as is the case in comparable studies
{cite}`bhattacharyya2011data`, since they offer little value 
while illustrating the general modelling framework and its interpretability. 
We retain only nine variables in our reduced dataset including the target variable 
`isFraud` which is an indicator of the transaction being fraudulent. 
Fig. 3 is a snapshot of the dataset with the variables 
included in our analyses.

![alt text](./images/data_output.pdf)
<p style="text-align: center;">
Fig. 3. Snapshot of the dataset.
</p>

We explore the dataset through a series of visualisations to 
get a better understanding of the variables in the data and their 
distributions. Fig. 4 is the distribution of the target 
variable `isFraud`, showing the severe imbalance in the proportion 
of fraudulent to normal transactions.

![alt text](./images/isFraud_barplot.pdf)
<p style="text-align: center;">
Fig. 4. Distribution of the target `isFraud`.
</p>

Fig. 5 is the distribution of the logarithm of the transaction 
amounts grouped by `isFraud`, where we observe the fraudulent 
transactions having a much smoother distribution over the transaction amounts. 
This could be an indication that fraudsters avoid multiple transactions with 
the same amount.

![alt text](./images/Amt_logd.pdf)
<p style="text-align: center;">
Fig. 5. Logarithm of the transaction amounts grouped by `isFraud`.
</p>

Fig. 6 is the distribution of the logarithm of the days since 
the last transaction grouped by `isFraud`, where we observe that 
fraudulent transactions are much likely to occur when there has been a 
previous transaction within the last 14 days. This could indicate that 
fraudulent activity is likely to cluster in time.

![alt text](./images/DaysSinceLast_logd.pdf)
<p style="text-align: center;">
Fig. 5. Logarithm of the days since last transaction grouped by `isFraud`.
</p>

Fig. 7 is a mosaic plot showing the two-dimensional distribution of the target 
`isFraud` along with another variable. The variable values along the 
y-axes are ordered with values having the smallest proportion of fraud at 
the top to the largest at the bottom. These figures show the distribution of 
the variable categories as well as help us recognise the categories with 
large fraud proportions.

![alt text](./images/CardType_mosaic.pdf)
<p style="text-align: center;">
Fig. 7. Mosaic plots showing the distribution of `isFraud` by various features.
</p>