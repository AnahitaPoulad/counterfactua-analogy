# Counterfactual Analogy
How to create counterfactuals using analogies

Counterfactuals explanations can be used to explain model predictions of individual instances. These counterfactuals describe minimal changes in the feature values at a specific point, required in order to acquire a different prediction in that instance. In the desired scenarios the prediction changes in a relevant way, like a flip in predicted class (for example, credit application accepted or rejected).

In this study we explore a method to generate counterfactual explanations, using analogies. We first generate a set of diverse counterfactuals for the our entire dataset w.r.t to a classifier using [DiCe](https://github.com/interpretml/DiCE) and keep only the nearest one w.r.t the gower metric, That would result in a set of X and X' pairs, in which X' is a counterfactual explanation for X according to our classifier. In order to generate a counterfactual explanation E' for a new instance E we try to solve the analogical equation x:X' :: E:?

We used the CNN analogy solver [nn-morpho-analogy](https://github.com/AmandineDecker/nn-morpho-analogy) for solving the analogies and evaluated our results with 2 metrics:
1. The number of feature differences (1/diff)
2. Class match (the portion of counterfactuals that show the class flip w.r.t our classifier) 

### How to use:
generating explanations when our dataset includes class labels is a simple three-step process: first you should train a classifier and then invoke DiCE to generate counterfactual examples and choose the closests, and finally initiate and train the analogy solver.

### Files and Folders:
```data``` : includes the datasets to replicate our results
```main``` : a demo of counterfactual generation using analogies
