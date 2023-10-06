# Experiment--02-Implementation-of-combinational-logic
Implementation of combinational logic using universal-gates
 
# AIM:
To implement the given logic function verify its operation in Quartus using Verilog programming.
 F1= A’B’C’D’+AC’D’+B’CD’+A’BCD+BC’D
F2=xy’z+x’y’z+w’xy+wx’y+wxy
 
 
 
# Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime


# Theory
Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output.

## USING NAND GATES:
NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate. So its output is
complement of the output of an AND gate.This gate can have minimum two inputs, output is always one. By using
only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR. So this gate is also called as 
universal gate. First note that the entire expression is inverted and we have three terms ANDed. This means that we 
must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression. Finally, negated single terms can 
be generates with a 2-input NAND gate acting as an inverted.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'

## USING NOR GATES:
Using NOR gates NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output
is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using 
only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called
universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with
NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and
NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'

## Logic Diagram
![D0](https://user-images.githubusercontent.com/119559827/233395286-5bc1a68f-09e0-4f69-aabc-f63d78b18589.png)


# Procedure
Step 1: Create a project with required entities.

Step 2: Create a module along with respective file name

Step 3: Run the respective programs for the given boolean equations.

Step 4: Run the module and get the respective RTL outputs.

Step 5: Create university program(VWF) for getting timing diagram.

Step 6: Give the respective inputs for timing diagram and obtain the results. 

Program to implement the given logic function using NAND and NOR gates and to verify its operations 
in quartus using Verilog programming.

# Program:
```
Program to implement the given logic function using NAND and NOR gates and to verify its operations in quartus using 
Verilog programming.
Developed by: PRAVEEN KUMAR S
RegisterNumber: 212222230108

module proj2(A,B,C,D,F1);
input A,B,C,D;
output F1;
wire x1,x2,x3,x4,x5;
assign x1 = (~A)&(~B)&(~C)&(~D);
assign x2 = (A)&(~C)&(~D);
assign x3 = (~B)&(C)&(~D);
assign x4 = (~A)&(B)&(C)&(D);
assign x5 = (B)&(~C)&(D);
assign F1 = x1+x2+x3+x4+x5;
endmodule

```
# RTL realization
![digital 02](https://github.com/Praveenkumar2004-dev/Experiment--02-Implementation-of-combinational-logic-/assets/119559827/c94fd5da-04b7-42ed-b8b5-20b3039b29dd)

# TRUTH TABLE:
![truth table](https://github.com/Praveenkumar2004-dev/Experiment--02-Implementation-of-combinational-logic-/assets/119559827/7e6a89d9-5e27-4a03-a1e9-52effd051f76)

## Output:
## Timing Diagram
![269825415-aa1ef37f-b4ed-42c1-90b2-6878a67ce975](https://github.com/Praveenkumar2004-dev/Experiment--02-Implementation-of-combinational-logic-/assets/119559827/3ef5704c-6fc5-4e18-b59c-166ff2059ee8)


# Result:
Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.
