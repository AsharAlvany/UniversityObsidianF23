Syntactic parsing - the task of recognizing a sentence and assigning a syntactic structure to it
Structural Ambiguity - occurs when the grammar can assign more than one parse to a sentence
![[Pasted image 20240306144533.png]]
	Here we can see that the phrase "in my pajamas" can either be a part of the verb phrase "shot an elephant in my pajamas", or the noun phrase "an elephant in my pajamas"
- attachment ambiguity - if a particular constituent can be attached to the parse tree at more than one place, leading to a separate meaning of the sentence
- coordination ambiguity - different sets of phrases that can be conjoined by a conjunction like "and"
<u>CKY Parsing</u> - dynamic programming parsing method. Classic example of the dynamic programming paradigm. Bottom-up parser.
- Must be in Chomsky Normal Form (CNF) - There must be only one terminal on the right hand side or two non-terminals
- The CNF conversion can be summarized as follows
	1. Copy all conforming rules to the new grammar unchanged
	2. Convert terminals within rules to dummy non-terminals
	3. Convert unit-productions
	4. Binarize all rules and add to new grammar
<u>Automatic Semantic Role Labeling</u> - identifies predicates and then identifies and further assigns thematic/semantic roles for each predicate
<u>Frames</u> - semantic representation of situations and characterized by
- Target words or lexical predicates whose meaning includes aspects of the frame
- Frame elements which represent the semantic roles of the frame
- Examples of annotations performed for instances of each target word in various texts
<u>Frame Relation</u> - a directed relation between two frames where one is called the Super_Frame (less dependent, more abstract) and the other frame is called the sub_frame.
![[Pasted image 20240325153040.png]]
