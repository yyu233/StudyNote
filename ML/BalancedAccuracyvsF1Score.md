```
Balanced Accuracy vs F1 Score
So you might be wondering what’s the difference between Balanced Accuracy and the F1-Score since both are used for imbalanced classification. So, let’s consider it.

F1 keeps the balance between precision and recall
F1 = 2 * ([precision * recall] / [precision + recall])
Balanced Accuracy = (specificity + recall) / 2
F1 score doesn’t care about how many true negatives are being classified. When working on an imbalanced dataset that demands attention on the negatives, Balanced Accuracy does better than F1.
In cases where positives are as important as negatives, balanced accuracy is a better metric for this than F1.
F1 is a great scoring metric for imbalanced data when more attention is needed on the positives. 
```
