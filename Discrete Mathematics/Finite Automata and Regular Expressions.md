Finite Automata are the simplest model of computation: computation is very limites, yet very useful in many different areas including compiler construction, switching theory, biology, communication protocols...

Define set of states, inputs, transitions of states based on states.

*What is an initial state?
What are accept/final states?
What are input sequences leading from init to an accept state?*

The state and input relationship is represented by diagrams and transition tables
![[Pasted image 20230831131624.png]]
	Where {0,1} are the inputs and $\{q_1, q_2, q_3\}$ are the states
![[Pasted image 20230831132641.png]]
	The double circle is the desired final state
___
#### Examples
![[Drawing 2023-09-05 13.11.05.excalidraw]]

---
### Nondeterministic Automata
Notated as NFA, has 0 to many outputs for some inputs
#### Subset Construction
![[Pasted image 20230907132322.png]]
![[Drawing 2023-09-07 13.11.48.excalidraw]]
![[Drawing 2023-09-07 13.34.15.excalidraw]]
### GNFA (Generalized Non Finite Automata)
A GNFA is an NFA in which transitions are labeled by REs
1. Ther must be a distinguishing initial state and a distinuished final state $q_0$ and $q_f$
2. Transitions are labeled by REs in R
**Converting NFA to GNFA**
- Transform N by shrinking GNFA to an GNFA with only two states
![[Pasted image 20230914131612.png]]![[Pasted image 20230914131705.png]]
Example:
![[Drawing 2023-09-14 13.17.38.excalidraw]]
