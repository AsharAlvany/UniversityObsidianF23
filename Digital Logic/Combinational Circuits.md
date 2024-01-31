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
