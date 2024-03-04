1. Design Model (input, output size, forward pass)
2. Construct loss and optimizer
3. Training loop
	1. forward pass: compute prediction
	2. backward pass: gradients
	3. update weights

Example 1:
```python
#the training set
X = torch.tensor([[1],[2],[3],[4]], dtype=torch.float32)
Y = torch.tensor([[2],[4],[6],[8]], dtype=torch.float32)
n_samples, n_features = X.shape
#4 samples and one feature because it is a one dimensional array
output_size = n_features
input_size = n_features
model = nn.Linear(input_size, output_size)
#the construction of the loss and optimizers
import nn from pytorch.nn
loss = nn.MSELoss()
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

Example 2:
```python
import torch
import torch.nn as nn
import numpy as np
from sklearn import datasets
import matplotlib.pyplot as plt

```