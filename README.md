# red-wine-quality-prediction

The aim of this project is to investigate and compare the effectiveness of Bayesian and non-Bayesian classification approaches for wine quality prediction using physicochemical properties as features. These properties include citric acidity, alcohol content, sulphates,volatile acidity,residual sugar,fixed acidity and so on. The classification models explored were Random forest, SVM, Relevance Vector Machine (RVM), MLP, Naive Bayes, KNN with the RVM being the Bayesian model.
The dataset used was the red variants of the Portuguese "Vinho Verde" wine from kaggle [1].

Due to a high class imbalance in the original data, classification
was explored using four approaches. Firstly, the data was modelled with the original quality classifications preserved.
Secondly, a binary classification of "Good" (scores 7 or above) vs "Bad" (below 7) was created to reduce the
number of imbalanced classes. Then, this binary classification was balanced using the SMOTE oversampling
method. Finally, an alternative binary classification was used where "Good" wines score 6 or
higher. Binary classification generally outperformed the original multi-class
approach. A threshold of >=6 and >=7 with SMOTE, offered a more balanced distribution between good
and bad classifications, while >=7 prioritized accurately identifying Bad wines. The optimal classification
threshold, however, depends on real world applications and domain knowledge.

Among the classification models evaluated, Random Forest generally achieved the highest overall accuracy.
Random Forests handle complex relationships well and are known to handle limited datasets and reduce
the risk of overfitting through its ensemble of decision trees. Naive Bayes had the poorest performance
possibly due to its feature independence assumption which doesn’t hold for all our features. However, its
low computational complexity makes it a very efficient option for high dimensional datasets. The Bayesian
model evaluated, the RVM did not perform as well as most non bayesian methods. This could possibly be
because the linear kernel was used for the model as a result of the computational time being too high while
using the RBF kernel, which captures complex relationships better. Irrespective of this, the RVM still showed
comparable results to the other models and even surpassed the naive bayes. An avenue for further work could
include investigating methods that can help to reduce the computational complexity of the RVM model.

A critical challenge this project faced is the class imbalance within the dataset. While undersampling
techniques were not explored in order to preserve the majority class, future research should utilize multiple
strategies. This could involve other data augmentation techniques, cost-sensitive learning, and potentially
acquiring more data points for the minority class.

## References
[1] UCI Machine Learning Repository, “Red Wine Quality Dataset,” Available online, 2009. URL https://www.
kaggle.com/uciml/red-wine-quality-cortez-et-al-2009, accessed: March 21, 2024.
