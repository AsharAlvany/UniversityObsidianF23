Parts of speech can be divided into two broad super-categories:
- closed class - those with relatively fixed membership, such as prepositions - new prepositions are rarely coined
- open class - classes that continually being created and borrowed
Nouns
- Proper nouns - are names of specific persons or entities
- Common nouns - are further divided
	- count nouns - allow grammatical enumeration, something that occurs in both the plural and singular
	- mass nouns - used when something is conceptualized as a homogeneous group
Verbs
- refer to actions and processes
Adjectives
- include many terms for properties or qualities
Adverbs - modifying something
- Directional adverbs - specify the direction or location of some action
- Degree adverbs - specify the extent of some action
- Manner adverbs - describe the manner of some action or process
- Temporal adverbs - describe the time that some action or event took place
Prepositions - occur before noun phrases
Particles - a particle resembles a preposition or an adverb and is used in combination with a verb
Phrasal verb - a verb and a particle that act as a a single syntactic and/or semantic unit are called a phrasal verb
<u>Hidden Markov Model</u> - a probablistic sequence model. Given a sequence of units it computes a **probability distribution** over possible sequences of labels and chooses the best label sequence
- An extension of finite automata![[Pasted image 20240221152358.png]]
<u>The Viterbi Algorithm</u> - the most common decoding algorithm for HMMs
- Input: a single HMM and a set of observed words
- Output: the most probable state/tag sequence with its probability
- The algo sets up a probability matrix or lattice