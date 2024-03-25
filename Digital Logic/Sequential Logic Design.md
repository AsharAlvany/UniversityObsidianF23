2- Glitch free circuits are circuits that have no independent prime implicants
- Sequential Circuits are digital circuits that the output depends on current input (combinational circuit) and the system state (a memory device to preserve the output value)
- Sequential Circuits are differentiated by times at which:
	- Storage elements observe inputs
	- Storage elements change their state
- Synchronous SC
	- Behavior is defined from knowledge of inputs at discrete instances of time
	- Storage elements observe inputs and can change state only in relation to a timing signal
- Asynchronous SC
	- Behavior is defined from knowledge of inputs at any instance of time
	- Storage elements observe inputs and change state at any point in time
- S-R Latches - basic async memory using set and release![[Pasted image 20240228181817.png]]
	- When S and R are 0, Q is kept in memory, When S is 0 and R is 1, Q is reset to 0, when S is 1 and R is 0, Q is set to 1
	- They have multiple design concerns
		- 1 and 1 input causes a distortion
		- The inputs are also responsible for the timing when the change should happen and to preserve the status. Ideally, they should only be responsible for the status change
- D Latch - builds on an S-R latch but only one input (01 and 10) as well as an enabler input![[Pasted image 20240304173758.png]]
	- There is undesired behavior when the Q' is connected to the D input in some way. The solution to this behavior is to break the closed path from Y to itself, by using a D flip=flop, which is built from two back-to-back D katches controlled by complementary clocks![[Pasted image 20240304174016.png]]
	- Whe clock is 0, the master is transparent and the slave is opaque. Hence, D value is propagated to N1
	- When the clock is 1, the master is opaque and the slave is transparent. Hence, N1 value is propagated to Q
	- From a timing perspective, whatever value is at N (between Q and D) immediately before the clock "rises" is copied to Q immediately "after" the clock "rises"
	- Therefore, a D flip-flop copies D to Q on the rising edge of the CLK, and remembers its state at all other times
<u>Registers</u>
- An N-bit register is a bank of N flip-flops that share a common CLK input, so that all bits of the register are updated at the same time
- Registers are the key building block of most sequential circuits
- In 4-bit registers, inputs D3:0 and outputs 03:0 are both 4-bit data busses
Resettable Flip-Flop - useful when trying to force all flip-flops into a state
- adds another input RESET to the flip flop
- when reset is false the resettable flip-flop behaves normally
- When the reset is true the resettable flip-flop ignores D and resets the output to 0
- Can be synchronously or asynchronously reset
<u>Synchronous Circuits</u>
- Only at the rising edge of the clock registers values along with other inputs can change the state of the circuit
- There are finite number of states the circuit can be in
- Every circuit element is either a register or a combinational circuit
- At least on circuit element is a register (otherwise it is a combinational circuit or an asynchronous sequential circuit)
- All registers receive the same clock signal
- Every cyclical path contains at least one register
<u>Finite State Machine</u>
- Composed of a known finite number of states
- One of them is special and is known as the start state
- It has set of transitions which determines how to move from one state to the next
- Conditions that tells the machine how to move from one state to the other
- Accepting states
<u>FSM Design Process</u>
- System level design a high-level description of the systems including inputs outputs and operations
- State transition diagram: description of all the states the system can be at with the possible transitions and transition conditions
- Create a State Transition Table and State Output Table
- Create a Binary encoding
- Assign numbers to all the states. This is crucial because it will tell how many memory cells are needed for the system
- Truth table - k-maps
<u>Moore Machine</u> - output depends only on the current state
<u>Mealy Machine</u> - depends on present state and current input
<u>State Encoding</u> - change the state of the circuit into binary to develop a truth table
<u>One Hot Encoding</u> - Each state has its own bit (4 states -> 4 bits)
<u>Binary Encoding</u> - Each state has its own combination (4 states -> 2 bits)
- $t_{ccq}$ - the shortest time when the output starts changing in response to the rising edge of the clock
- $t_{pcq}$ - the longest time allowes before the Q settles to the final value
- To sample the ipnut value D properly, the input must be stabilized at least
	- $t_{setup}$ minimum time the ipnut(s) is stable before the clock rising edge
	- $t_{hold}$ minimum time the input(s) is stable after the clock rising edge
	- The sum of the setup and hold times are the aperture times![[Pasted image 20240325175147.png]]
<u>System Timing</u>
- $T_c$ is the time between rising edges of a repetitive clock signal
- $f_c = \frac{1}{T_c}$ is the clock frequency, increasing the clock frequency increases the work that a digital system can accomplish per unit time
- 