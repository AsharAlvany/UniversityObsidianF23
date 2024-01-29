- Combinational Logic (Ability to perform an operation)
	- Uses basic gates
	- Used for data operations
	- Time is not a parameter
- Sequential Logic (Ability to control an operation)
	- Allows for controls and flow branching
	- Used to implement memory
	- Time is a parameter
- The purpose is to design and build architectures that are
	1. Reliable secure and safe
	2. Energy efficient
	3. Predictable and low latency
	4. Specialized for key industries and domains (AI/ML, Genomics, VR, etc)
- Evaluation Criteria for the Design (BALANCE)
	- Functionality
	- Reliability
	- Space Requirements
	- Cost
	- Expandibility
	- Comfort Level
	- Security
	- Others
---
### Basic Concepts

- **Analog** means continuous. It expresses the smooth gradual change of parameters
- **Digital** means to operate using parameters that have limited discrete values. These parameters change by jumping from one allowed value to another
- Easier to work with digital, conversion from analog to digital is common, this process is called digitization
- Lossless digitization is not possible
- Number Representation
- Positional Number System (examples decimal, octal, binary, etc.)
- To convert from decimal to another positional system divide the decimal number by the positional system identifier (binary: 2, octal: 8) until you have 0, storing the remainder in a list (left-to-right, then flip), to get the 
### Binary, octal, and hexadecimal conversion
- The maximum that a hexadecimal digit can be represented by is three binary bits because 8 (octal) is a power of 2 (binary) ($2^3 = 8$) 
	- $(011 101 011 111 101 011 101)_2 = (3537535)_8$
	- Because I split the binary into segments of length 3 starting from the right
	- Likewise, 16 is a power of 2 (hexadecimal -> binary)
- The highest value that can be represented of any base r with n digits is $r^n -1$
	- 999 = $10^3-1$
### Fractional Representation
- $(2409.87)_{10} = 2\cdot 10^3 + 4\cdot 10^2 + 0\cdot 10^1 + 9 + 8\cdot10^{-1} + 7\cdot10^{-2}$
### Signed Numbers
- To represent a signed number, most often in binary a 2's complement is used
- Sign-Magnitude Representation
	- The sign bit is 0 means positive and 1 means negative
	- Simple, but it cuts the maximum number that is able to represented is cut in half $2^{n-1} -1$
	- And there are two representations of zero (+ and -)
	- Addition and subtraction costs are increased
- 1's Complement (2r - 1 complement)
	- Given a binary number N, the 1's complement of N is obtained by flipping each bit in N
		- $(1010101)_2 = (0101010)_2$
	- If the most significant digit is a one then it is a negative number, if it is a zero then it is unsigned (positive)
	- A range of $2^n - 1 -n$
	- Still has positive and negative zero, but quicker to add/subtract
- 2's Complement
	- The given binary number N, the 2's complement of N=1's complement + 1
		- $(01101001)_2 = (10010110)_2$
		- $(10010110)_2 + 1 = (10010111)_2$
	- Range is $2^N-1$
	- Faster method
		- Start from the least significant 1 (right-most one)
		- Leave all to the right unchanged 
		- Flip all the bits to the left
	- Numerical Value of a 2's complement using expansion - just expand like normal but if most significant bit is 1 then make the base of the exponent of the leading digit a 1
		- $(1101)_2 = -2^3+ 2^2 + 0 + 1 = (-3)_{10}$
---
### Boolean Algebra
- AND
	- $X$ AND $Y = X.Y = XY$
	![[Pasted image 20240124183711.png]]
- OR
	- $X$ OR $Y = X+Y$
	![[Pasted image 20240124183743.png]]
- NOT
	- NOT $X = ~X=X'=\bar{X}$
	![[Pasted image 20240124183756.png]]
- NAND - NOT AND
	![[Pasted image 20240124184010.png]]
- NOR - NOT OR
	![[Pasted image 20240124184209.png]]
- XOR - EXCLUSIVELY OR (Either one or the other must be true, but NOT both)
	![[Pasted image 20240124184423.png]]
- 