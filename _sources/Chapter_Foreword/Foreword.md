# Foreword

Real-time governance is best described by the three-step process, as 
illustrated in Fig. 1.

![alt text](./images/rtg.pdf)
<p style="text-align: center;">
Fig. 1. Process flow diagram for real-time governance.
</p>

It involves the tasks of detecting threats to a system, understanding those 
threats and then taking appropriate action to deal with them. Broadly speaking, 
real-time governance can be broken down into two strategies, namely, threat 
modelling and anomaly detection.

Threat modeling works by identifying the types of threat agents that cause harm 
to a system, via a thorough analysis of the software architecture, business 
context, and functional specifications. This process enables a deeper 
understanding and discovery of important aspects of the system. Following 
identification of the threats, they are then prioritized and recommendation for 
mitigation are also provided. Typically, threat modeling is performed during 
the design stage (but it can occur at other stages) of a new system to help 
developers find vulnerabilities and become aware of the security implications 
of their design, code, and configuration decisions.

However, in complex real-world systems, threat modelling alone might not be 
sufficient to detect all threats. The task of identifying such unknown threats 
falls under the general problem of anomaly detection. Detecting anomalies, 
those defined to give rise to high impact but have a low probability of 
occurring, is a challenge in a number of domains including meteorological, 
environmental, financial and economic. The use of machine learning to identify 
anomalies is becoming increasingly popular, since they offer an effective and 
scalable solution when compared to traditional signature-based methods. 

In this book, we present techniques that can 
be used in a framework for employing machine learning methods for anomaly 
detection. While the book focuses on 
the specific case of fraud detection, we believe that most of the 
techniques and discussions presented in this book can be useful to other 
practitioners working on the wider topic of anomaly detection.