(Fraud_Detection_System)=
# Fraud detection system

A credit card Fraud Detection System (FDS) is typically composed of a set of five layers of control, as illustrated in Fig. 1. 
![alt text](./images/FDS.jpg)
<p style="text-align: center;">
Fig. 1. Diagram illustrating the layers of control in an FDS. Our focus in this book is mostly on the data-driven model, which helps investigators by raising alerts on the most suspicious transactions.
</p>

The first two layers (*Terminal* and *Transaction Blocking Rules*) are executed in real-time (i.e. within milliseconds and before authorization). The next two layers (*Scoring Rules* and *Data-Driven Model (DDM)*), are executed in near real-time to potentially block the card and prevent additional frauds. Finally, the last layer (Investigators) is the only one requiring human intervention and is carried out offline.

Effective detection requires both a mix of automated systems and fraud investigators. This has non-trivial implications. First, automated systems should optimize the workload of fraud investigators. Second, automated systems and human investigators work at different time scales: while automated systems usually provide risk scores for transactions in less than a second, fraud investigations usually require contacting a client to confirm a fraud, which can take days, or weeks.