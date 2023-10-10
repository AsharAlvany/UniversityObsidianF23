### Elimination of Useless Symbols
![[Pasted image 20231010131948.png]]
- Starting by collecting only the letters that can result in a nonterminal
- Then continue by collecting letters that can be arrived at
- B and F can be turned into a nonterminal string b {B, F} -> p1
- S and A can be arrived at because B and F are already collected {A, B, F, S} -> p2
- E can now be collected because we now have A {A, B, C, F, S} -> p3
- Nothing else can be collected so the negation of p3 are the nonproductive symbols