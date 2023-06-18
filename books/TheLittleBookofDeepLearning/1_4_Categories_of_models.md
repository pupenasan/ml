[<---   1.3 Недостатнє навчання та перенавчання](1_3_Under_and_overfitting.md)         [Зміст](README.md)          [2__Efficient_computation.md    --->](2__Efficient_computation.md) 

## 1.4    Categories of models

We can organize the use of machine learning models into three broad categories:

- **Regression** consists of predicting a continuous-valued vector $y ∈ R^K$, for instance, a geometrical position of an object, given an input signal $X$. This is a multi-dimensional generalization of the setup we saw in [§1.2](1_2_Basis_function_regression.md). The training set is composed of pairs of an input signal and a **ground-truth** value.
- **Classification** aims at predicting a value from a finite set $\{1,...,C\}$, for instance, the label $Y$ of
  an image $X$. As for regression, the training set is composed of pairs of input signal, and groundtruth quantity, here a label from that set. The standard way of tackling this is to predict one score per potential class, such that the correct class has the maximum score.
- **Density modeling** has as its objective to model the probability density function of the data $μ_X$ itself, for instance, images. In that case, the training set is composed of values $x_n$ without associated quantities to predict, and the trained model should allow either the evaluation of the probability density function, or sampling from the distribution, or both.

Both regression and classification are generally referred to as **supervised learning** since the value to be predicted, which is required as a target during training, has to be provided, for instance, by human experts. On the contrary, density modeling is usually seen as **unsupervised learning** since it is sufficient to take existing data, without the need for producing an associated groundtruth.

These three categories are not disjoint; for instance, classification can be cast as class-score regression, or discrete sequence density modeling as iterated classification. Furthermore, they do not cover all cases. One may want to predict compounded quantities, or multiple classes, or model a density conditional on a signal.

