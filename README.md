## Demo Propensity Model ##

At its core, a propensity model is basically a predictive ML model where marketing campaign parameters are the input features (X values) and the results of each customer encounter, for example, are the output feature (the Y value). For a predictive model, the general goal is to configure that model such that we achieve optimal accuracy. When we're thinking about the model in the context of marketing, we can relate the accuracy of the model to avoidable cost or unrealized revenue. In the dataset used in this demo, each sample represents a customer encounter that either results in a successful sale or a failed attempt. 

* If the model predicted success but should have predicted failure, that's an avoidable cost: A more accurate model would have told us not to contact that customer.
* If the model predicted failure but should have predicted success, that's unrealized revenue: We didn't contact that customer because the model predicted a failure. A more accurate model would have told us to contact the customer.

There are other things we may want to do to the model in the context of a marketing campaign. For example, we may want not extract a _contact_ or _don't contact_ result from the model. If our campaign is time constrained, we may want to extract the probability of success for each customer so that we can order our contacts by highest to lowest probability.

This model is implemented in a Jupyter Notebook, based on a [bank marketing dataset](https://archive.ics.uci.edu/ml/datasets/Bank+Marketing). Besides the usual python data libraries, also makes use of the [imbalanced-learn API](https://imbalanced-learn.org/stable/over_sampling.html) to allow more control over the balance of categories in the train and test partitions used not just for model training, but also for model evaluation. It also lets us have a consistent train/test dataset regardless of the model or evaluation type and we don't have to depend on the model having a "balance" option. Also uses the [Predictive Power Score library](https://towardsdatascience.com/rip-correlation-introducing-the-predictive-power-score-3d90808b9598) for feature selection.

**TO-DO:**
1. Add the imbalanced-learn splitting.
2. Tune hyperparameters.
3. Look at other models.
4. General clean-up.