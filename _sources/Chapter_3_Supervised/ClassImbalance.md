(Tackling_class_imbalance)=
# Tackling class imbalance

The challenge of working with imbalanced datasets is that most machine 
learning algorithms will ignore, and in turn have poor performance on, the 
minority class, although particularly in the case of rare event 
detection, it is performance on the minority class that is most important. 
Popular approaches for tacking class imbalance are based on sampling and 
they can be classified into three categories:

1. **Over-sampling**, by adding more examples of the minority class 
so it has more effect on the machine learning algorithm. In over-sampling, 
instead of creating exact copies of the minority class examples, we can 
introduce small variations into those copies, creating more diverse synthetic 
samples.
2. **Under-sampling**, by removing some examples of the majority 
class so it has less effect on the machine learning algorithm. In 
under-sampling we can cluster the examples of the majority class, and do 
the under-sampling by removing examples from each cluster, thus seeking to 
preserve information.
2. **Hybrid**, a mix of over-sampling and under-sampling.

## SMOTE: Synthetic Minority Over-Sampling Technique

As listed above, one approach to addressing imbalanced datasets is to 
over-sample the minority class. The simplest approach involves duplicating 
examples in the minority class, although these examples don’t add any new 
information to the model. Instead, new examples can be synthesised from 
the existing examples by introducing small variations and is referred to 
as the Synthetic Minority Oversampling Technique {cite}`chawla2002smote`, 
or SMOTE for short.

SMOTE works by selecting examples that are close in the feature space, 
drawing a line between the examples in the feature space and creating a 
new sample at a point along that line. Specifically, a random example 
from the minority class is first chosen. Then k of the nearest 
neighbours for that example are found (typically k=5). A randomly 
selected neighbour is chosen and a synthetic example is created at a 
randomly selected point between the two examples in feature space.

The approach is effective because new synthetic examples from the 
minority class are created that are plausible as they are relatively 
close in feature space to existing examples from the minority class. 
A general downside of the approach is that synthetic examples are 
created without considering the majority class, possibly resulting 
in ambiguous examples if there is a strong overlap for the classes.

We apply SMOTE to balance the classes in our dataset and assess its 
impact in the following ways. Fig. 8 gives the absolute 
difference of the mutual information (MI) among all pairs of features 
between transactions grouped by the target `isFraud`. The results 
are shown before (top) and after (bottom) the application of SMOTE. The 
absolute differences of MI are comparatively higher after SMOTE 
indicating that the pairwise feature relationships are more distinct 
between the two classes after balancing. 

![alt text](./images/MI_after_smote.pdf)
<p style="text-align: center;">
Fig. 8. The absolute difference of the mutual information (MI) between transactions grouped by `isFraud` before (left) and after (right) applying the SMOTE technique to balance the classes. The absolute differences of MI are higher after SMOTE indicating that the pairwise feature relationships are more distinct between the two classes after balancing.
</p>

A popular method for exploring high-dimensional data is t-SNE, introduced 
by {cite}`maaten2008visualizing`, an unsupervised and non-linear 
dimensionality reduction technique. Fig. 9 gives the 
results of applying t-SNE to visualise the dataset in a reduced 
two-dimensional space both before (top) and after (bottom) using SMOTE to 
balance the classes. The classes appear to be relatively more separable 
after the application of SMOTE.

![alt text](./images/tsne_smote.pdf)
<p style="text-align: center;">
Fig. 7.Dimensionality reduction using t-SNE before (left) and after (right) using SMOTE to balance the classes. The classes appear to be more separable after the application of SMOTE.
</p>