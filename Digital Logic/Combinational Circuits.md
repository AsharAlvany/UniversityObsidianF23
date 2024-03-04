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
<u>7-Segment Display Decoder</u> - takes a 4-bit data input, D3:0, and produces seven outputs to control light-emitting diodes to display a digit from 0 to 9
- The seven outputs are often called segments a through g or $S_a - S_g$
- These seven outputs will signify a number
<u>Don't Care in Outputs</u> - the "don't care" symbol can appear in the truth table outputs where the output values is unimportant, or the corresponding input combination can never happen
- These symbols can be treated as either a 0 or a 1 and can be changed depending on the kmap groupings (prime implicates)
<u>Multiplexers</u> - combinational logic is often grouped into larger building blocks o build more complex systems such as the priority circuit and the 7-segment display decoder
- MUX - chooses an output from among several possible inputs (typically $2^n$)based on the value of a select signal. The bit combination of the selection lines determines an n-bit binary number whose decimal equivalent corresponds to the subscript of the selected input terminal
- 3 multiplexers can create a bigger multiplexer![[Pasted image 20240219182418.png]]
- Applications of Multiplexers - Use the multiplexer as a lookup table to prerecord the values needed on the prototype so there is no need to redesign or rebuild
	- When a MUX is used as a look-up table then the select lines for the MUX become the elements of the function that is being simulated and the inputs are hard-wired to either be on or off based on the functionality of the function that is being simulated![[Pasted image 20240221173554.png]]
<u>Combining rows from truth tables</u>
- If we want to combine two rows together the right most variable can be eliminated and we can still express the function output value of the combined rows as either 0, 1, or the right most variable was elminated (where b is an arbitrary leftmost column)
	- Scenario 1: if the result remains the same, the remove b and keep the output the same
	- Scenario 2: if the result is dependent on column b and the result reflects that column, then the output can be shown in terms of b
	- Scenario 3: if the result is dependent on column b and the result reflects the opposite of column b, then the output can be shown in terms of b\`
<u>Decoder</u> - is a $n \cdot m$ combinational circuit that converts binary information from n input lines m output lines where $m <= 2^n$
- output values of decoders are mutually exclusiv exactly one output is 1 for any given input combination (address)
<u>Hierarchial Decoder Design</u>
- 2 smaller decoders can be equivalent to one larger decoder if there is an enabler circuit utilized (without the or gate needed in the MUX version)
<u>Timing</u>
- We assumed that there is a 0-time for input values to propagate through the combinational circuit to produce the output
- Rising edge- the transition of a signal from low to high
- Falling edge - the transition of a signal from high to low
- 50% Point - is the point when a signal is between high and low
- Propagation Delay - the maximum time from when an input changes until the output or outputs reach their final value
	- Categorized by the critical path
- Contamination Delay - the minimum time from when an input changes until any output starts to change its value
- <u>Time Glitches</u> - can be caused because the circuit design will cause the output to do multiple transitions before it becomes steady. Usually not a problem as long as we wait until the propagation delay elapse. Sometimes the glitch can be critical