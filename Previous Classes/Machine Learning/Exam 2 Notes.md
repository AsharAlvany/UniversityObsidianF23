Machine Learning is a method of data analysis that automates analytical model building
- Supervised Learning
	- Labeled data and are trying to predict a label based off of known features
	- Classification, regression, prediction, and gradient boosting
- Unsupervised Learning
	- You have unlabeled data and are trying to group together similar data points based off of features
	- Nearest-neighbor mapping, k-means, and singular value decomposition
- Reinforcement Learning
	- Algorithm learns to perform an action from experience
	- The algorithm discovers through trial and error the solution to the problem, this king of analytical model is comprised of two main components - the agent and the environment
A perceptron consists of one or more inputs a processor and a single output. A perceptron follows the feed forward model meaning inputs are sent into the neuron, are processed and result in an output
Input Layers - real values from the data
Hidden Layers - layers in between input and output, 3 or more layers is a deep network
Output Layer - Final estimate of the output
Activation Functions: sigmoid, hyperbolic tangent, **rectified linear unit**
Gradient Descent Algorithms: SGC, Adam, Adadelta, Adagrad, RMSProp
![[Pasted image 20231212173200.png|500]]
**Code:**
- Load csv to dataframe
`USAhousing = pd.read_csv('USA_Housing.csv')`
- Load a dataset from tensorflow/keras
```python
from tensorflow.keras import datasets
dataset = datasets.cifar10.load_data()
(train_images, train_labels), (test_images, test_labels) = dataset
(X_train, y_train), (X_test, y_test) = dataset
```
- Load a dataset from sklearn
```python
from sklearn.datasets import load_iris
iris = load_iris()
df = pd.DataFrame(iris.data, columns=iris.feature_names)
df.target = iris.target
```
- Pairplot
`sns.pairplot(USAhousing)`
- Display a plot (the default is a histogram) and show a kernel density estimation
`sns.displot(USAhousing["Price"], kde = True)`
- Display a scatterplot
```python
plt.figure(figsize=(7,5)) # size of figure
ax = sns.scatterplot(x="exam_score1", y="exam_score2", hue='admission_decision', data=df, style='admission_decision', s=80)
handles, labels = ax.get_legend_handles_labels()
ax.legend(handles[:], ['None admitted', 'Admitted'])
plt.title('Scatter plot of training data')
plt.show()
```
- Create a heat-map
`sns.heatmap(glue, annot=True)`
- Set up a train, test, and split
```python
from sklearn.model_selection import train_test_split
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.33, random_state=42)
```
- Metrics
```python
from sklearn.metrics import confusion_matrix, classification_report
print(modelG.score(X_test, y_test))
print(modelM.score(X_test, y_test))
print(modelB.score(X_test, y_test))
```
**Linear Regression:**
- Least Squares is a statistical method used to determine a line of best fit by minimizing the sum of the squares created by a mathematical function ("up and down")
- The goal is to minimize the vertical distance between all the data points and our line
```python
from sklearn.linear_model import LinearRegression
ln = LinearRegression()
ln.fit(X_train, y_train)
print(ln.intercept_, ln.coef_)
prediction= ln.predict(X_test)
```
**Logistic Regression:**
```python
from sklearn.linear_model import LogisticRegression
clf = LogisticRegression(max_iter=2000)
clf.fit(X_train,y_train)
predictions = clf.predict(X_test)
```
**ANN (Artificial Neural Network)**
- Architecture: an input layer, one or more hidden layers, and an output layer.
- Functionality: suited for regression and classification problems. Image and speech recognition, natural language processing, and more
- Training: involves adjusting the weights based on the error between the predicted output and the actual output using techniques such as back propagation
```python
from tensorflow.keras import layers, models
ann = models.Sequential([
    layers.Flatten(input_shape=(32, 32, 3)),
    layers.Dense(3000, activation='relu'),
    layers.Dense(1000, activation='relu'),
    layers.Dense(10, activation='sigmoid')
])
ann.compile(optimizer='SGD', loss='sparse_categorical_crossentropy', metrics='accuracy')
ann.fit(X_train, y_train, epochs = 5)
y_pred = ann.predict(X_test)
y_pred_classes = [np.argmax(element) for element in y_pred]
```
**CNN (Convolutional Neural Network)**
- Architecture: Designed for grid-like data such as images. Consists of convolutional layers, pooling, layers, and fully connected layers. Convolutional layers use filters to capture spatial hierarchies in the data
- Functionality: Object detection, image classification, and image segmentation
- Training: CNNS are trained using back propagation similar to ANNs but with additional considerations for convolutional and pooling layers
```python
from tensorflow.keras import layers, models
cnn = models.Sequential([
    layers.Conv2D(filters=32, kernel_size=(3,3), activation='relu', input_shape=(32,32,3)),
    layers.MaxPooling2D((2,2)),
    layers.Conv2D(filters=64, kernel_size=(3,3), activation='relu', input_shape=(32,32,3)),
    layers.MaxPooling2D((2,2)),

    layers.Flatten(),
    layers.Dense(64, activation='relu'),
    layers.Dense(10, activation='softmax'),    
])
cnn.compile(optimizer='adam', loss='sparse_categorical_crossentropy', metrics=['accuracy'])
cnn.fit(X_train, y_train, epochs=10)
cnn.evaluate(X_test, y_test)
```
**RNN (Recurrent Neural Network)**
- Architecture: RNNs are designed to handle sequential data by maintaining a hidden state that captures information about previous inputs.
- Functionality: RNNs are used for tasks where the order of the input data is important such as natural language processing, speech recognition, and time series events
- Training: training RNNs, requires back propagation through time. Traditional RNNs suffer from vanishing and exploding gradient problems
**Hidden Markov Chains**
![[Pasted image 20231212154715.png|500]]
**Naive Bayes**
- Independence Assumption, Classification
$$P(A|B) = \frac{P(B|A) \cdot P(A)}{P(A)}$$
```python
from sklearn.naive_bayes import GaussianNB, MultinomialNB, BernoulliNB
modelG = GaussianNB()
modelM = MultinomialNB()
modelB = BernoulliNB()
```
**SVC/SVD**
- Classification
```python
from sklearn.svm import SVC
# C, kernel, gamma are hyperparameters
model = SVC()
model.fit(X_train, y_train)
model.score(X_test, y_test)
```
**K-Folds**
- K-Folds Give every sub component to be a part of the learning process and take an average (different from Random Forest Trees where the outcome is the popular vote) 
```python
from sklearn.model_selection import KFold
from sklearn.ensemble import RandomForestClassifier #default estimators is 100
kf = KFold(n_splits=3)
kf
```
**Random Forest Classifier**
```python
from sklearn.ensemble import RandomForestClassifier
model = RandomForestClassifier(n_estimators=60)
model.fit(X_train, y_train)
model.score(X_test, y_test)
```