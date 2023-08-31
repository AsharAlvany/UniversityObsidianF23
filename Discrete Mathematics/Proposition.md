A [[Proposition]] is a type of [[logic]] declarative sentence that is either true or false. Propositional calculus was first created by [[Aristotle]].

__The main functions within propositional logic are:
* Negation --<sub>|</sub>p, which is a logical not\
	* "not p"
* Conjunction p ^ q, which is a logical and
	* "p and q"
* Disjunction p v q, which is a logical or
	* "p or q"
* Implication -p > q, which is a logical if-then
	* "if p then q"
	* "q unless not p"
* Biconditional p <--> q, which is a two way conditional
	* "p if and only if"

__Logical Precedence:
1. Negations
2. Conjunction
3. Disjunction
4. Implication
5. Biconditional

**System of specifications** - specifications of a system should be consistent , there should not be any contradictions
> "The diagnostic message is stored in the buffer or it is transmitted"
> "The diagnostic message is not stored in the buffer"
> "If the diagnostic message is stored in the buffer, then it is transmitted"
>
	p = "diagnostic message is stored in the buffer"
	q = "transmitted" 
>
> p v q
> --<sub>|</sub> p
> p -> q
>
>p = F and q = T

**[[De Morgan's Law]]** :
* --<sub>|</sub> (p ^ q) = --<sub>|</sub>p v --<sub>|</sub>q
* --<sub>|</sub> (p v q) = --<sub>|</sub>p ^ --<sub>|</sub>q