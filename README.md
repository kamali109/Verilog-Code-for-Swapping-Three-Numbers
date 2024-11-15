## EXPERIMENT-03 VERILOG CODE FOR SWAPPING THREE NUMBERS

## Aim:
```
To design and simulate a Verilog HDL code for swapping the values of three numbers without using any temporary variables, and verify the correctness of the swapping operation through a testbench using the Vivado 2023.1 simulation environment.
```
## Apparatus Required
```
Vivado 2023.1 or equivalent Verilog simulation tool.
```
## Procedure:
```
Launch Vivado 2023.1:

Open Vivado and create a new project.
Write the Verilog Code for Swapping:

Write the Verilog code that swaps the values of three numbers (a, b, and c) using basic arithmetic or bitwise operations without using temporary variables.
Create the Testbench:

Write a testbench to simulate the swapping operation. The testbench should initialize three numbers, trigger the swapping module, and check if the values are swapped correctly.
Add the Verilog Files:

Add the Verilog module and the testbench file to the Vivado project.
Run Simulation:

Run the behavioral simulation in Vivado to verify the swapping operation.
Observe the Waveforms:

Examine the waveform to confirm that the values of the three numbers are swapped as expected.
Save and Document Results:

Capture the waveform output and include the results in your report for verification.
```
## Verilog Code:
```
// swap_three_numbers.v
module swap_three_numbers (
    input wire [7:0] a_in,
    input wire [7:0] b_in,
    input wire [7:0] c_in,
    output reg [7:0] a_out,
    output reg [7:0] b_out,
    output reg [7:0] c_out
);
    always @(*) begin
        a_out = b_in; // Swap: a = b
        b_out = c_in; // Swap: b = c
        c_out = a_in; // Swap: c = a
    end
endmodule
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/836e8e39-4b16-434c-8119-453cf3c9e07e)
![image](https://github.com/user-attachments/assets/6fab65d9-0448-4c6b-900d-5fe5733fc493)
![image](https://github.com/user-attachments/assets/8dee0b00-16a2-4e3e-b84b-a7303146b744)

## Testbench for Swapping Three Numbers:
```
// swap_three_numbers_tb.v
`timescale 1ns / 1ps

module swap_three_numbers_tb;

    // Inputs
    reg [7:0] a;
    reg [7:0] b;
    reg [7:0] c;

    // Outputs
    wire [7:0] a_out;
    wire [7:0] b_out;
    wire [7:0] c_out;

    // Instantiate the Unit Under Test (UUT)
    swap_three_numbers uut (
        .a_in(a),
        .b_in(b),
        .c_in(c),
        .a_out(a_out),
        .b_out(b_out),
        .c_out(c_out)
    );

    // Test procedure
    initial begin
        // Initialize inputs
        a = 8'd10; // Assign 10 to a
        b = 8'd20; // Assign 20 to b
        c = 8'd30; // Assign 30 to c

        // Wait for 10 ns to observe swap
        #10;

        // Display results
        $display("Before Swap: a = %d, b = %d, c = %d", a, b, c);
        #10;
        $display("After Swap: a = %d, b = %d, c = %d", a_out, b_out, c_out);
        
        // Stop the simulation
        #10 $stop;
    end
endmodule
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/7a387a13-b7b6-4348-9992-c6fe2ccd14e0)

## Conclusion:
```
In this experiment, a Verilog HDL code for swapping three numbers was designed and successfully simulated. The testbench verified the swapping operation, showing that the values of three input numbers (a, b, and c) were swapped correctly without the use of temporary variables. This experiment demonstrated the effectiveness of Verilog in implementing logical operations and control mechanisms such as swapping values. The simulation results confirm the correct functionality of the design.
```
