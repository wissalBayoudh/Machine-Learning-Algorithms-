# 1.. Classification and Regression Tree (CART)
A classification tree is obtained by a recursive partitioning of the entry space.
## Decision Tree Parameters
- criterion str, optional (default=”gini”) : The function to measure the quality of a split.
Supported criteria are “gini” for the Gini impurity and “entropy” for the information gain.
- min_samples_split int, float, optional (default=2) : The minimum number of samples required to split an internal node
- min_samples_leaf: The minimum number of samples needed to be considered a leaf node. The default value is set to one. Use this parameter to limit the growth of the tree.
### Advanced: Overfitting and Underfitting
In practice, it’s not uncommon for a tree to have 10 splits between the top-level (all data) and a leaf. As the tree gets deeper, the dataset gets sliced up into leaves with fewer data. If a tree only had 1 split, it divides the data into 2 groups. If each group is split again, we would get 4 groups of data. Splitting each of those again would create 8 groups. If we keep doubling the number of groups by adding more splits at each level, we’ll have 210210 groups of data by the time we get to the 10th level. That’s 1024 leaves.
When we divide the data amongst many leaves, we also have fewer data in each leaf. Leaves with very few data will make predictions that are quite close to those homes’ actual values, but they may make very unreliable predictions for new data (because each prediction is based on only a few data).
This is a phenomenon called overfitting, where a model matches the training data almost perfectly but does poorly in validation and other new data. On the flip side, if we make our tree very shallow, it doesn’t divide up the data into very distinct groups.
At an extreme, if a tree divides data into only 2 or 4, each group still has a wide variety of data. Resulting predictions may be far off for most data, even in the training data (and it will be bad in validation too for the same reason). When a model fails to capture important distinctions and patterns in the data, so it performs poorly even in training data, that is called underfitting.
Since we care about accuracy on new data, which we estimate from our validation data, we want to find the sweet spot between underfitting and overfitting. Visually, we want the low point of the (red) validation curve in the image shown below.










Ressources :
- [sklearn.tree.DecisionTreeClassifier](https://scikit-learn.org/stable/modules/generated/sklearn.tree.DecisionTreeClassifier.html)
- [Machine Learning Basics: Decision Tree From Scratch](https://towardsdatascience.com/machine-learning-basics-descision-tree-from-scratch-part-ii-dee664d46831)
