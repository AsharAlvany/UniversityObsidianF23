- Information Gain
	- In order to pick which feature to split on we need a way of measuring how good the split is. This is where information gain and entropy come in.
- ID3 (Iterative Dichotomize)
	- Uses information theory (entropy) to split on an attribute that gives the highest information gain
	- Entropy is a measure of the impurity on a distribution calculates for a discrete random variable Y taking m distinct values 
	$$H(x) = \sum^{n}_{i=1} -P_i \log_2P_i$$
	- High Entropy means all classes are nearly equally likely
	- Low Entropy means that a few classes are likely, most of the classes are rarely observed