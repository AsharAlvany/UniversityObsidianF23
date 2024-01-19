### Elimination of Useless Symbols
![[Pasted image 20231010131948.png]]
- Starting by collecting only the letters that can result in a nonterminal
- Then continue by collecting letters that can be arrived at
- B and F can be turned into a nonterminal string b {B, F} -> p1
- S and A can be arrived at because B and F are already collected {A, B, F, S} -> p2
- E can now be collected because we now have A {A, B, C, F, S} -> p3
- Nothing else can be collected so the negation of p3 are the nonproductive symbols
### Elimination of Chain Productions
**Chain Productions**
![[Pasted image 20231012132500.png]]
**Elimination of unnecessary chains**
![[Pasted image 20231012133118.png]]
### Chonisky Normal Form
A CFG G is in CNF if every production is of form 
![[Pasted image 20231012133219.png]]