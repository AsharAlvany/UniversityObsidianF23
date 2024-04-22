<u>feedforward networks</u> can be trained to make predictions about the next word, unfortunately, their cons are that they limit the context from which information can be extracted
A <u>recurrent neural network</u> is any network that contains is a cycle within its network connections
![[Pasted image 20240417150548.png]]
<u>Simple Recurrent Network (SRN) Elman Networks</u> - The hidden layer from the previous timestep provides a form of memory, or context, that encodes earlier processing and informs the decisions to be made at later points in time.
- Given an input vector and the values for the hidden layer from the previous time step, we’re still performing the standard feedforward calculation![[Pasted image 20240417150922.png]]
- Using this figure, we are using the weights from the previous timestep, U, to affect the the $h_t$ layer. These weights will be trained via backpropagation
<u>Forward inference</u> - the mapping of a sequence of inputs to a sequence of outputs in an RNN is nearly identical to what we have already seen with ffnn, where g is the suitable activation function
![[Pasted image 20240417151229.png]]
The following figure shows the sequential nature of SRN by unrolling the network in time![[Pasted image 20240417151350.png]]
<u>Training the RNN</u>
- use a training set
- use a loss function
- backpropagation to update the sets of weights in the RNN
	- W, the weights from the input layer to the hidden layer
	- U, the weights from the previous hidden layer to the current hidden layer, and
	- V, weights from the hidden layer to the output layer
<u>Backpropagation training for RNN</u> - two-pass algo
- Forward inference, computing $h_t$, $y_t$, and a loss at each step in time, saving the value of the hidden layer at each step for use at the next time step
- process the sequence in reverse, computing the requred error terms gradient as we go, computing and saving the error tem for use in the hidden layer for each step backward
<u>RNN as Language Models</u>
- INPUT: a sequence x that consists of word embeddings represented as one-hot vectors of size $|V| \times 1$
- OUTPUT: the output predictions, y, are represented as vectors representing a probability distribution over the vocabulary
<u>RNN for sequence classification</u>
- INPUT: a word at a time which would generate a new hidden layer at each step/ The hidden layer for the final element of the text is taken to constitute a compressed representation of the entire sequence