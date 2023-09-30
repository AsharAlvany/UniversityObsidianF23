Context Free Grammars are useful in describing the syntax of natural or programming languages. ![[Pasted image 20230926131247.png]]
aSa, aBa, bB, and b are called **productions**
![[Pasted image 20230926131424.png]]
to show **equivalence** of languages use the following terminolgy (highlighted in yellow)
![[Pasted image 20230926131709.png]]
![[Pasted image 20230926132051.png]]
**Derivation Trees** - visualize the derivation process
![[Pasted image 20230926132326.png]]
	The tree above describes a language with the same number of a's and b's
The **frontier** of a tree is the string obtained by concatenating the labels of the leaves of T from left to right. If the frontier of T is a terminal string then T is a **terminal derivation tree** 
**How to generate CFG**
![[Pasted image 20230926133900.png]]
1. Basis: $\varepsilon \epsilon L$ 
2. Recursive Step: If $x, y \epsilon L$, then so are $a \cdot b, b \cdot a, xy$  
### Regular Grammars
A **regular grammar** is a grammar of the form
![[Pasted image 20230928135249.png]]
