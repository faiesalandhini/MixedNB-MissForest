# MixedNB-MissForest
Klasifikasi Hepatitis Dengan Imputasi MissForest Menggunakan Mixed Naive Bayes

API

class mixed_naive_bayes.MixedNB(categorical_features=None, max_categories=None, alpha=0.5, priors=None, var_smoothing=1e-09)

Naive Bayes classifier for Categorical and Gaussian models.

Note: When using categorical_features, MixedNB expects that for each feature, all possible classes are captured in the trining data X in the mixed_naive_bayes.mixed_naive_bayes.MixedNB.fit method. This is to ensure numerical stability.

Parameters
categorical_features (array-like shape (num_categorical_classes,) or) –

(default=None) ('all') – Columns which have categorical feature_distributions

max_categories (array-like, shape (num_categorical_classes,) (default=None)) – The maximum number of categories that can be found for each categorical feature. If none specified, they will be generated automatically.

alpha (non-negative float, optional (default=0)) – Additive (Laplace/Lidstone) smoothing parameter (0 for no smoothing). This is for features with categorical distribution.

priors (array-like, size (num_classes,), optional (default=None)) – Prior probabilities of the classes. If specified, the priors are not adjusted according to the data.

var_smoothing (float, optional (default=1e-9)) – Portion of the largest variance of all features that is added to variances for calculation stability.

priors
probability of each class.

Type
array, shape (num_classes,)

epsilon
absolute additive value to variances

Type
float

num_samples
number of training samples

Type
int

categorical_features
number of classes (number of layes of y)

Type
int

gaussian_features
the distribution for every feature and class

Type
array, shape (num_classes,)

categorical_posteriors
the distribution of the categorical features

Type
array

theta
the mean of the gaussian features

Type
array

sigma
the variance of the gaussian features

Type
array

References

https://scikit-learn.org/stable/modules/classes.html#module-sklearn.naive_bayes

Example

from mixed_naive_bayes import MixedNB
X = [[0, 0, 180, 75],
         [1, 1, 165, 61],
         [2, 1, 166, 60],
         [1, 1, 173, 68],
         [0, 2, 178, 71]]
y = [0, 0, 1, 1, 0]
clf = MixedNB(categorical_features=[0,1])
clf.fit(X,y)
clf.predict(X)
