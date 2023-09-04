Machine Learning is a subdomain of computer science that focuses on algorithms that help a computer learn from data without explicit programming

AI vs ML vs DS -

- AI is an area of computer science where the goal is to enable machines and computers to perform human-like tasks and simulate human behavior
- Machine learning is a subset of AI that tries to solve a specific problem and make predictions using data
- Data science is a field that attempts to find patterns and draw insights from data

Three types of machine learning -

1. Supervised learning - uses labeled inputs to train models and learn outputs
2. Unsupervised learning - uses unlabeled data to learn about patterns in data
3. Reinforcement learning - agent learning in interactive environment based on rewards and penalties

Feature Vector is a list of all the data that we are inputting to find a trend within to determine an output (or the target for the feature vector)

Feature matrix is the accumulation of all of the feature vectors

Targets vector is the accumulation of all the targets

Different types of datasets - why do we need different datasets? we need to make sure that out model can generalize from the data and for that reason we often break up our datasets into three partitions

1. Training Dataset - Feed this dataset into the model, find the loss (the difference between the output and the intended result), make adjustments rerun until loss is at a manageable level
2. Validation Dataset - Feed this dataset into the model, find the loss (the difference between the output and the intended result), make last minute adjustments
3. Testing Dataset - Feed this dataset into the model, find the loss (the difference between the output and the intended result), whatever loss is reported is the general loss of your model

Loss is the difference between prediction and label. Loss is reported in the following mathematical ways

- L1 Loss - an absolute function (where y sub r is the real output and y sub p is the predicted output)

$$ LOSS = SUM( |y_r - y_p|) $$

- L2 Loss - a quadratic function (where y sub r is the real output and y sub p is the predicted output)

$$ LOSS = -1/N *SUM(y_r * log(y_p)+(1-y_r)*log(1-y_p))) $$

- Binary Cross-Entropy Loss - Loss decreases as the performance gets better, but this only works with binary outputs

$$ LOSS = SUM( |y_r - y_p|) $$

Accuracy - percentage of correctly identified targets

k-nearest neighbors is a simple, supervised machine learning algorithm that can be used to solve both classification and regression problems, where k is the number of neighbors that the model tests against (usually 3 or 5)

Precision - Out of all the retrieved data, how much was actually relevant (out of all the ones the model predicted to be correct, how many truly were correct?)

Recall - Out of all the relevant data, how much did the model retrieve (out of all the correct data, how much did the model capture)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/2b0bbaa9-df17-4b7b-bce0-9aaac5f324bc/Untitled.png)

Bayes’ Theorem -

$$ P(A|B) = (P(A) * P(B|A))/P(B)

$$

$$ P(B)=ΣP(B|A)*P(A) $$

Naive Bayes’ Classifier - Naive Bayes’ Classifier utilizes Bayes’ rule to construct a classifier for new data based on test data. Given that we have 2 classifications (A and B), with k characteristics (x1, x2, x3, … xk), we can create a classification table that uses relative proportionality to predict which classification to assign to other instances. Naive Bayes’ Classifier is termed as “naive” because it does not take the order of characteristics into account.

$$ P(A)*Π_1^k(P(x_1 | A )) $$

Naive Bayes’ Classifier - Naive Bayes’ Classifier utilizes Bayes’ rule to construct a classifier for new data based on test data. Given that we have 2 classifications (A and B), with k characteristics (x1, x2, x3, … xk), we can create a classification table that uses relative proportionality to predict which classification to assign to other instances. Naive Bayes’ Classifier is termed as “naive” because it does not take the order of characteristics into account.

$$ P(A)*Π_1^k(P(x_1 | A )) $$