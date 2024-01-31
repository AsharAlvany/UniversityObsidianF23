<u>Soundex</u>  - class of heuristics to expand a query into phonetic equivalents
- Turn every token to be indexed into a 4-character reduced form![[Pasted image 20240129145212.png]]
		Herman becomes H655 (hermann will create the same code)
<u>N-Grams</u> - used for word prediction
- Count the number of tokens (including punctuation)
<u>Wordform</u> - fully inflected surface form
Brute force method of estimating how likely a word would occur after a string of words: $P(w_n |w_1 ,w_2…w_{n-1} )$
<u>Maximum Likelihood Explanation</u>
![[Pasted image 20240129153344.png]]
Evaluation Method
- <u>Perplexity</u> - an approximation used to evaluate N-grams in an intrinsic evaluation
	- The perplexity on a test set is the inverse probability of the test set, normalized by the number of words (OG, chain rule, bigrams)
		![[Pasted image 20240131151758.png]]![[Pasted image 20240131151811.png]]![[Pasted image 20240131151817.png]]
	- When there is a word in the test corpus that was never seen in the training corpus, the perplexity becomes positive infinity
	- Maximizing probability is the same as minimizing perplexity
- Standard method - the training and test set
- <u>Smoothing</u> - the task of re-evaluation some of the zero-probability and low-probability estimations. Using either Laplace smoothing technique or the good-turing discounting techniques to modify the MLE for computing N-grams to always assign them nonzero values
- <u>Laplace (Add-One) Smoothing</u> - The simplest way to do smoothing is to add 1 to all the ngram counts, before we normalize them into probabilities. All the counts that used to be zero will now have a count of 1, the counts of 1 will be 2, and so on. (Applied to the unigram model: )
	![[Pasted image 20240131152931.png]]
- <u>Discounting</u> - another method of smoothing![[Pasted image 20240131154408.png]]![[Pasted image 20240131154125.png]]![[Pasted image 20240131154253.png]]![[Pasted image 20240131154350.png]]![[Pasted image 20240131154324.png]]
	