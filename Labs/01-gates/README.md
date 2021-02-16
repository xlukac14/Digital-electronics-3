# Lab assignment 01-gates

## 1. Repository link 
Link to my repository: [tmarcak/Digital-electronics-1](https://github.com/tmarcak/Digital-electronics-1)

## 2. De Morgan's Law
Link to EDA playground: [De Morgan's Law](https://www.edaplayground.com/x/8Pat)

### Equations
![](Images/Equations.png)

### VHDL
```vhdl
library ieee;               -- Standard library
use ieee.std_logic_1164.all;-- Package for data types and logic operations

------------------------------------------------------------------------
-- Entity declaration for basic gates
------------------------------------------------------------------------
entity gates is
    port(
        a_i    : in  std_logic;         -- Data input
        b_i    : in  std_logic;         -- Data input
        c_i	   : in  std_logic;         -- Data input
        f_o    : out std_logic;         -- OR output function
        fnand_o: out std_logic;         -- AND output function
        fnor_o : out std_logic          -- XOR output function
    );
end entity gates;

------------------------------------------------------------------------
-- Architecture body for basic gates
------------------------------------------------------------------------
architecture dataflow of gates is
begin
    f_o  <= ((not b_i) and a_i) or ((not c_i) and (not b_i));
    fnand_o <= not (not (not b_i and a_i) and not(not b_i and not c_i));
    fnor_o <= (not (b_i or not a_i)) or (not (c_i or b_i));

end architecture dataflow;
```

### Table
| **c** | **b** |**a** | **f(c,b,a)** |
| :-: | :-: | :-: | :-: |
| 0 | 0 | 0 | 1 |
| 0 | 0 | 1 | 1 |
| 0 | 1 | 0 | 0 |
| 0 | 1 | 1 | 0 |
| 1 | 0 | 0 | 0 |
| 1 | 0 | 1 | 1 |
| 1 | 1 | 0 | 0 |
| 1 | 1 | 1 | 0 |

### De Morgan's Law Simulation
![](Images/Screenshot_1.1.png)


## 3. Distribution Laws
Link to EDA playground: [Distribution Laws](https://www.edaplayground.com/x/88pG)

### Equations
![](Images/Distributives.png)

### VHDL
```vhdl
library ieee; 				-- Standard library
use ieee.std_logic_1164.all;-- Package for data types and logic operations

------------------------------------------------------------------------
-- Entity declaration for basic gates
------------------------------------------------------------------------

entity gates is
    port(
        a_i    	 : in  std_logic; -- Data input      
        b_i    	 : in  std_logic; -- Data input    
        c_i    	 : in  std_logic; -- Data input     
        dist1_o  : out std_logic; -- Left side of first distribution law output function
        dist2_o  : out std_logic; -- Right side of first distribution law output function
        dist3_o  : out std_logic; -- Left side of second distribution law output function
        dist4_o  : out std_logic  -- Right side of first distribution law output function
    );
end entity gates;

------------------------------------------------------------------------
-- Architecture body for basic gates
------------------------------------------------------------------------

architecture dataflow of gates is
begin
    dist1_o <= (a_i and b_i) or (a_i and c_i);
	dist2_o <= a_i and (b_i or c_i);
    dist3_o <= (a_i or b_i) and (a_i or c_i);
    dist4_o <= a_i or (b_i and c_i);
end architecture dataflow;
```

### Distribution Laws simulation
![](Images/Screenshot_1.2.png)






