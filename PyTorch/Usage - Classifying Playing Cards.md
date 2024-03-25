Import Packages
```python
import torch
import torch.nn as nn
import torch.optim as optim
from torch.utils.data import Dataset, DataLoader
import torchvision.transforms as transforms
from torchvision.datasets import ImageFolder
import timm #architectures for image classications

import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
```
PyTorch dataset (and dataloader)
```python
class PlayingCardDataset(Dataset):
	def __init__(self, data_dir, transform=None):
		self.data = ImageFolder(data_dir, transform=transform)

	def __len__(self):
		return len(self.data)

	def __getitem__(self, idx):
		return self.data[idx]

	@property
	def classes(self):
		return self.data.classes
```
Augment the images to decrease variability while training
```python
transform = transforms.Compose([
	transforms.Resize((128,128)),
	transforms.ToTensor(),
])
data_dir = 'dir/of/images'
dataset = PlayingCardDataset(data_dir, transform)
```
Dataloader - batching our dataset by parallelizing the reading of our data
```python
dataloader = DataLoader(dataset, batch_size=32, shuffle=True)
```
PyTorch Model - create the model from scratch, defining each layer, however for tasks like image classification, many of the state of the art architectures are readily available and we can import them from packages like timm, understanding the pytorch model is all about understanding the shape the data is at each layer, and the main one we need to modify for a task is the final layer. here we have 53 targets, so we will modify the last layer for this.
```python
class SimpleCardClassifier(nn.Module):
	def __init__(self, numClasses=53):
		# define all the parts of the model
		super(SimpleCardClassifier, self).__init__()
		self.base_model = timm.create_model('efficientnet_b0', pretrained=True)
		self.features = nn.Sequential(*list(self.base_model.children())[:-1])
		enet_out_size = 1280
		# make a classifier
		self.classifier = nn.Linear(enet_out_size, num_classes)
	
	def forward(self, x):
		# Connect these parts and return the output
		x = self.features(x)
		output = self.classifier(x)
		return output
```
Training - optimizer, loss (Adam works well in most cases)
```python
criterion = nn.CrossEntropyLoss()
optimizer = optim.Adam(model.parameters(), lr=0.001)

train_folder = 'dir/to/train'
val_folder = 'dir/to/val'
test_folder = 'dir/to/test'

train_dataset = PlayingCardDataset(train_folder, transform=transform)
val_dataset = PlayingCardDataset(val_folder, transform=transform)
test_dataset = PlayingCardDataset(test_folder, transform=transform)

train_loader = DataLoader(train_dataset, batch_size=32, shuffle=True)
val_loader = DataLoader(val_dataset, batch_size=32, shuffle=False)
test_loader = DataLoader(test_dataset, batch_size=32, shuffle=False)
```
Training loop
```python
device = torch.device("cuda:0" if torch.cuda.is_available() else "cpu")
num_epoch = 5
train_loss, val_loss = [], []

model = SimpleCardClassifier(num_classes=53)
model.to(device)

for epoch in range (num_epochs):
	model.train()
	running_loss = 0.0
	for images, labels in train_loader:
		images, labels = images.to(device), labels.to(device)
		optimizer.zero_grad()
		outputs = model(images)
		loss = criterion(outputs,labels)
		loss.backward()
		optimizer.step()
		running_loss += loss.item() * inputs.size(0)
	train_loss = running_loss / len(train_loader.dataset)
	train_losses.append(train_loss)
	
	# Validation Phase
	model.eval()
	running_loss = 0.0
	with torch.no_grad():
		for images, labels in val_loader:
			outputs = model(images)
			loss = criterion(outputs, labels)
			running_loss += loss.item() * inputs.size(0)
	val_loss = running_loss / len(val_loader.dataset)
	val_losses.append(val_loss)
```