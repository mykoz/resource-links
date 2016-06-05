##Random Forests


Christine
@cfhurtab

ML is a subset of AI

Entropy - referring to as _information gain_ in machine learning

The random forest learning algorithm uses a close concept to information gain as the cost function:  Gini Impurity

k = number of observations at that node.

A random forest creates many trees.
Each tree is trained on a random subset of data (bagging)
A subset of features is tested for each tree (default is sqrt of (# of vars))
The minimum number of terminal nodes varies depending on if it's a classification (1) or regression (5)

As the number of nodes in a tree increases, it will reduce the training error.  However, true error will be later increased.

ROC curve
x:  False positive rate
y:  True positive rate

caret in R will help with grid search

scikit-learn - can use RandomForestClassifier right out of the box
n_estimators - very important; might want to change
max_depth - want to think about
min_samples_leaf - want to think about

want to go from numerical and categorical values to same type
categorical vars --->  dummy variables
60 vars - do 1 0 hot encoding
get dummies in pandas also works

Python
class sklearn.grid_search.GridSearchCV
default param:  accuracy
accuracy is always 70% no matter what I use (since 70% of flights are late)
most problems, care about AUC
change to scoring='auc_roc'

Number of trees
usually, the more the better, but runtime grows linearly

Max Depth of Trees
 - too small underfits
 - too large overfits

Min sample leaf size
 - 
 
Train-Test-Validation
If you do grid search, you can overfit your data
Keep 3rd data set:  Validation

optimal number will depend on your dataset

Recall
Random Forests - it takes a lot of work to interpret random forests

Tips
- check for overfitting
- 
- use AUC, not accuracy
- precision - recall - queue rate is useful in business settings
- visualize to understand the model
- if data is too big, try random sub-sampling















