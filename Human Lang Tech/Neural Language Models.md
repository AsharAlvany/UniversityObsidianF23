Neural networks are an essential computational tool for language processing and a very old one. A modern neural network is a network of small computing units, each of which takes a vector of input values and produces a single output value. The neural architecture we focus on is called a <u>feed-forward network</u> because the computation proceeds iteratively from one layer of units to the next.
A neural network is like a network of logistic regression classifiers and rather than forming the features by feature templates, the prior layers of the network induce the feature representation themselves
Each layer propagates the weight of the previous layer to the next layer.
The building blocks of neural networks are <u>neurons</u>. A unit takes a set of real valued numbers as input, performs some computation on them, and produces output
<u>neural unit</u> is taking a weighted sum of its inputs, with one additional term in the sum called a bias term. His creates a set of inputs ($x_1...x_n$) with a set of corresponding weights ($w_1...w_n$) and a bias b so the weighted sum can be represented as $$z=+\sum_iw_ix_i$$
<u>Activation Functions</u> - the types of non-linear functions that can be applied to z
- sigmoid function - takes a real value and maps it to the range \[0,1]. Tends to squash outliers. $y=a=f(z)$ where y is the neural network output, a is the activation value, and z (a linear function of x). However, the sigmoid function is not commonly used as an activation function. This is because very high values of z result in values of y that are extremely close to 1![[Pasted image 20240214145414.png]] 
- tanh - a variant of the sigmoid function that ranges from -1 to +1. But this activation function is much more complicated to be used on every neuron
	  ![[Pasted image 20240214145733.png]]
- ReLU - the simplest activation function and perhaps the most commonly used is a rectified linear unit, also called the ReLU
	  ![[Pasted image 20240214145934.png]]
  In the standard architecture, <u>each layer is fully-connected</u>, meaning that each unit in each layer takes as input the outputs fully-connected from all the units in the previous layer
  - softmax function - used to normalize outputs of the (LAST LAYER) hidden layer to result in a vector that encodes a probability distribution
    ![[Pasted image 20240214151142.png]]
Pros of NN for Language Models
- Don't need smoothing
- Can handle longer histories
- Generalize over contexts of similar words
- Much higher predictive accuracy than an n-gram language model
Cons
- Strikingly slower to train than traditional language models, and so for many tasks an n-gram language model is still the right tool
Projection Layer:
- In the projection layer, we concatenate the embeddings of the previous context
	![[Pasted image 20240219152218.png]]