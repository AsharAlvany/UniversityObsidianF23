Entity and Architectire are the two most used modules in HDL Languages:
- Entity: is a block of hardware with input and outputs
- Architecture: The description of the internal build (functionality) of an entity
- There are two common models:
	- Behavioral: it describes what an entity or a module does
	- Structural: it describes how an entity or a module is built from smaller components
```VHDL
library IEEE;
use IEEE.STD_LOGIC_1164.all;
entity tristate is
	port (a: in STD_LOGIC_VECTOR (3 downto 0);
	en: in STD_LOGIC;
	y: out STD_LOGIC_VECTOR (3 downto 0));
end;
architecture synth of tristate is
begin
y <= “ZZZZ” when en = ‘0’ else a;
end;
```
```VHDL
library IEEE; use IEEE_STD_LOGIC_1164 all;
entity flop is
	port (clk: in STD_LOGIC;
	d: in STD_LOGIC_VECTOR (3 downto 0));
	q: out STD_LOGIC_VECTOR (3 downto 0));
end;
architecture synth of flop is
begin
	process (clk) begin
	-- if RISING_EDGE(clk) then
	--		q < = d;
	--	end if;
	--	if clk'event and clk = '1' then
			q < = d;
		end if;
	end process;
end;
```
	Here the "process" keyword as an event listener which is extremely important for use as a register
```VHDL
library IEEE; use IEEE.STD_LOGIC_1164.all;
entity flopr is
	port (clk. reset: in STD_LOGIC;
	d: in STD_LOGIC_VECTOR (3 downto 0) ;
	q: out STD_LOGIC_VECTOR (3 downto 0)) ;
end;
architecture asynchronous of flopr is
begin
	process (clk, reset) begin
		if reset = ‘1’ then
			q <= “0000”;
		elsif clk’ event and clk ‘1’ then
			q <= d;
		end if;
	end process;
end;
```
	Here we utilize a reset input as a part of the async circuit
```VHDL
library IEEE; use IEEE.STD_LOGIC_1164.all;
entity flopenr is
	port (clk, reset, en: in STD_LOGIC;
	d: in STD_LOGIC_VECTOR (3 downto 0);
	q: out STD_LOGIC_VECTOR (3 downto 0));
end;
architecture asynchronous of flopenr is
-- asynchronous reset
begin
	process (clk, reset) begin
		if reset = ‘1’ then
			q <= “0000”;
		elsif clk’event and clk = ‘1’ then
			if en = ‘1’ then
				q <= d;
			end if;
		end if;
	end process;
end;
```
```c++
void arb_function(int n) {
	for (int i = n; i > 0; i--){
		arb_function(i-1);
	}
}
```