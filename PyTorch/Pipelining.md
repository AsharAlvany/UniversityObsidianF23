1. Design Model (input, output size, forward pass)
2. Construct loss and optimizer
3. Training loop
	1. forward pass: compute prediction
	2. backward pass: gradients
	3. update weights

Example 1:
```python
import torch
import nn from pytorch.nn
#the training set
X = torch.tensor([[1],[2],[3],[4]], dtype=torch.float32)
Y = torch.tensor([[2],[4],[6],[8]], dtype=torch.float32)
n_samples, n_features = X.shape
#4 samples and one feature because it is a one dimensional array
output_size = n_features
input_size = n_features
#model = nn.Linear(input_size, output_size)
class LinearRegression(nn.Module):

	def __init__(self, input_dim, output_dim):
		super(LinearRegression, self).__init__()
		# define layers
		self.lin = nn.Linear(input_dim, output_dim)
	def forward(self, x):
		return self.lin(x)

model = LinearRegression(input_size, output_size)
#the construction of the loss and optimizers
loss = nn.MSELoss()
#Stochastic Gradient Descent
learning_rate = 0.01
n_iters = 100
optimizer = torch.optim.SGD(model.parameters(), lr=learning_rate)

#example of the training loop
for epoch in range(n_iters):
	#forward
	y_pred = model(X)
	# loss
	l=loss(Y, y_pred)
	#gradients
	l.backward()
	#update weights
	optimizer.step()
	#zero the gradients
	optimizer.zero_grad()
	print(f"loss =  {l.8f}")
print(f"Prediction after training: f(5) = {model(X_test).item():.3f}")
```

Example 2 Linear Regression:
```python
import torch
import torch.nn as nn
import numpy as np
from sklearn import datasets
import matplotlib.pyplot as plt

#0) prepare data
X_numpy, Y_numpy = datasets.make_regression(n_samples=100, n_features=1, noise=20, random_state=1)
# convert tensors
X = torch.from_numpy(X_numpy.astype(numpy.float32))
y = torch.from_numpy(Y_numpy.astype(numpy.float32))
# format the features to become a multidimensional tesnor
y = y.view(y.shape[0], 1)
n_samples, n_features = X.shape
#1) model
input_size = n_features
output_size = 1
model = nn.Linear(input_size, output_size)
#2) loss and optimize
learning_rate = 0.01
criterion = nn.MSELoss()
optimizer = torch.optim.SGD(model.parameters(), lr=learning_rate)
#3) training loop
num_epochs = 100
for epochs in range(num_epochs):
	# forward pass and loss
	y_predicted = model(X)
	loss = criterion(y_predicted, y)
	# backward pass
	loss.backward()
	# update
	optimizer.step()
	# empty our gradients because it will sum up the gradients into the optimizer grad parameter
	optimizer.zero_grad()
	# check the loss and progress
	print(f"epoch{epoch-1}, loss = {loss.item():.4f}")

predicted = model(X).detach().numpy()
plt.plot(X_numpy, y_numpy. "ro")
plt.plot(X_numpy, predicted, "b")

```
Example 3 Logistic Regression
```python
import torch
import torch.nn as nn
import numpy as np
from sklearn import datasets
from sklearn.preprocessing import StandardScaler
from sklearn.model_selection import train_test_split
#0) Prepare zero
bc = datasets.load_breast_cancer()
X, y = bc.data, bc.target

n_samples, n_features = X.shape
print(n_samples, n_features)

# split
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=0)
#

```
