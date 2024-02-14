- <u>A digital circuit</u> is composed:
	- An item is a circuit which implements some logical function
	- A node is a connection that connects to external input, ouput, or some between inner items
- Two classes of digital logic circuits
	- Combinational circuits - depends only on the current values of the input (memory-less)
	- Sequential circuits - depends on both the current and previous input values (has memory)
- Combinational Circuits must meet three conditions
	- Every element is itself combinational
	- Every node is either designated as an input or  to the circuit  or connects to exactly one output terminal of a circuit element
	- The circuit contains no cyclical 
- Operator Precedence:
	- Parenthesis
	- NOT
	- AND
	- OR
- <u>Dual</u> - obtain the dual of a function by replacing the or's to and's and the 1's to 0's as well as vice versa (to both)
	- Every expression that comes to a true value has an equivalent truth value for the dual function
	
| Expression | Duality | Postulate |
| ---- | ---- | ---- |
| x + 0 = x | x.1 = x | Identity Element |
| x + 1 = 1 | x.0 = 0 | Domination |
| x + x = x | x . x = x | Identity |
| x + x\` = 1 | x.x\` = 0 | Complement |
| x\`\` = x | x\`\` = x | Involution |
| x + y = y + x | x.y = y.x | Commutative |
| (x + y) + z = x + (y + x) | (x.y).z = x.(y.x) | Associative |
| x.(y + z) = (x.y) + (x.z) | x + (y.z) = (x + y).(x + z) | Distributive |
| (x + y)\` = x\`.y\` |  x\`.y\` = (x + y)\` | DeMorgan's |
- <u>Complement</u> - complement of a function is obtained by interchaging of 0's for 1's in the values of F in the truth table
	- Apply DeMorgan's Law by taking the function and just negating it and distributing using DeMorgan's Law
	- Also can find the dual and negate all the terms
### Canonical Form
- <u>Minterms</u> - also known as the standard product is the product (AND) of ALL input variables where each variable is in the normal or the complement state
		- xyz, x\`y\`z\`, x\`yz, x\`y\`z, ... -> there are $2^n$ minterms
		- From the truth tables, a minterm can be derived with each variable primed if the corresponding bit is 0, or unprimed otherwise
		- Given $m_{N}$ the maxterm designation is built on the binary representation of N
- <u>Maxterms</u> - also known as the standard sums is the sum (OR) of ALL input variables where each variable is in the normal or complement state
		- x+y, x\`+y\`, x\`+y, x+y\`  -> there are $2^n$ maxterms
		- From the truth table a maxterm can derived with each variable primed if the corresponding bit is 1, or unprimed otherwise
		- Given $M_{N}$ the maxterm designation is built on the binary representation of N
- <u>Sum-of-Minterm (SOM) Canonical Form</u> - Also known as sum of product boolean function can be expressed algebraically from a given truth table by
		- Generate all the minterms of the input combinations that produce an output value of 1
- <u>Converting to SOM Form</u>
		- <u>Truth Table Approach</u> - Create the truth table of the expression, identify the minterms (where the resulting is 1) from the table and generate the SOM
		- <u>Algebraic manipulations</u> - Change the expression into a SOP, for each missing literal x in a term, multiply the term by (x + x\`), simplify the expression as needed
- <u>Converting to POM Form</u>
		- <u>Truth Table Approach</u> - Create the truth table of the expression. identify the maxterms (where the resulting is 0) from the table and generate the POM
		- <u>Algebraic Manipulations</u> - Re-structure the expression in product terms such that each term is composed of sum of individual literals only, by adding AA\'
- <u>Standard Order</u> - make sure all variables are represented in a form that you choose consistently (alphabetically)
<u>Function Complement</u> - the complement of a function expressed as a sum of minterms is constructed by selecting the minterms missing in the SOM canonical form
<u>NAND Gate</u> - implemented efficiently in CMOS tech in terms of chip area and speed (NOT AND also INVERT-OR)
- Unlike AND and OR, the NAND and NOR operations are not associative
<u>NAND-NAND Implementation</u>  - REMEMBER BUBBLE PUSH LOOK AT NOTES
<u>NOR-NOR Implementation</u> - REMEMBER BUBBLE PUSH LOOK AT NOTES
<u>Schematic Design</u> - it is crucial to use clear guidelines hen drwaing digital circuits from the logic function or truth table
- Inputs are on the left
<u>Multiple Output Circuit</u> - in many cases there are more than one output required to carrt out the desired function behavior
<u>XOR</u> - function behavior odd number of ones results in a true+++
<u>Circuit Optimization</u> - K-Map is a simple algorithm procedure to simplify Boolean functions
<u>K-Maps</u> - (Karnaugh Map) is a diagram made of a collection of adjacent squares
- Only works with canonical form
- Each square represents a minterm
- The collection of squares is a graphical representation of a Boolean function
	![[Pasted image 20240212174254.png]]
