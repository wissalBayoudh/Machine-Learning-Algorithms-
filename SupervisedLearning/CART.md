# 1.. Classification and Regression Tree (CART)
A classification tree is obtained by a recursive partitioning of the entry space.
## Decision Tree Parameters
- **criterion** str, optional (default=”gini”) : The function to measure the quality of a split.
Supported criteria are **“gini”** for the Gini impurity and **“entropy”** for the information gain.
#### What an Entropy basically does?
Entropy controls how a Decision Tree decides to split the data. It actually effects how a Decision Tree draws its boundaries.
- **min_samples_split** int, float, optional (default=2) : The minimum number of samples required to split an internal node
- **min_samples_leaf**: The minimum number of samples needed to be considered a leaf node. The default value is set to one. Use this parameter to limit the growth of the tree.











Ressources :
- [sklearn.tree.DecisionTreeClassifier](https://scikit-learn.org/stable/modules/generated/sklearn.tree.DecisionTreeClassifier.html)
- [Machine Learning Basics: Decision Tree From Scratch](https://towardsdatascience.com/machine-learning-basics-descision-tree-from-scratch-part-ii-dee664d46831)
