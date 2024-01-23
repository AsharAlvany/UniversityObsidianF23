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
### Fractional Representaion
- $(2409.87)_{10} = 2\cdot 10^3 + 4\cdot 10^2 + 0\cdot 10^1 + 9 + 8\cdot10^{-1} + 7\cdot10^{-2}$
### Signed Numbers
