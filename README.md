# EVM 
 Digital design of EVM machine with the help of fsm
 ## Problem statement ->
In this circuit EVM machine is designed assuming 4 candidates. 
The requirement of this circuit would be to be able to store the value of the number of votes of the candidates standing in elections,
when the button is pressed the number of votes should increase by 1 for that candidate. 

## Explaination of code ->
### Module Declaration:
Defines a module named EVM with inputs (reset, A, B, C, D, evaluate) and output (winner). Reset is a control input to reset the system.
A, B, C, D are inputs representing votes for each candidate. 
Evaluate is an input signal indicating the need for evaluation. winner is a 2-bit output representing the winning candidate.

### Internal Registers and Wires:
Defines internal registers (count_A, count_B, count_C, count_D, count, temp, temp1, temp2, state, next_state, clk, win) and wires (change, C1, C2, C3) for various purposes such as counting votes, storing temporary values, and controlling the FSM.

### Clock Generation:
Generates a clock signal clk with a period of 3 time units.

### Initial Block:
Initializes registers and states to default values at the start of simulation.

### Finite State Machine (FSM):

State Control: Defines the FSM states (start, button_tapped, count_plus_A, count_plus_B, count_plus_C, count_plus_D, pause, comp1, comp2, comp3, result) and transitions between them based on input conditions.
State Transition Logic: Determines the next state based on the current state and input conditions.

Counter Logic: Increments the count register when in the pause state.

### Counting Operation:
Increments the respective candidate count registers (count_A, count_B, count_C, count_D) based on the current state.

### Comparison Logic:
Compares the counts of candidates in successive stages of the FSM (comp1, comp2, comp3) to find the candidate with the highest count.

### Winner Determination:
Determines the winning candidate based on the comparison results.

### Output Assignment:
Assigns the winning candidate's identifier to the winner output.

