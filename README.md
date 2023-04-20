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

Using NAND gates:

module NAND(A,B,C,D,F);
input A,B,C,D;
output F;
wire P,Q,R;
assign P=(~(~C & B & A));
assign Q=(~(~D & C & A));
assign R=(~(C & ~B & A));
assign F=~(P & Q & R);
endmodule

Using NOR gates:

module NOR(A,B,C,D,F);
input A,B,C,D;
output F;
wire P,Q,R,S;
assign P = (C & ~B & A);
assign Q = (D & ~C & A);
assign R = (C & ~B & A);
assign S = (~(P | Q | R));
assign F = (~S);
endmodule
```
# RTL realization

## Output:
## RTL FOR NAND:
![D1](https://user-images.githubusercontent.com/119559827/233392219-3f043b17-92c7-4dae-b731-3e2d80374b24.png)
## FOR NOR:
![D2](https://user-images.githubusercontent.com/119559827/233392666-1fcfa57b-e129-41fc-ba04-b46a356dffbf.png)

## Timing Diagram
## FOR NAND:
![DD1](https://user-images.githubusercontent.com/119559827/233396232-8b508797-6264-4935-aba1-479217e47919.png)

## FOR NOR:
![DD2](https://user-images.githubusercontent.com/119559827/233396446-ca509ac2-e3d2-48c4-bcc3-779875b29022.png)

# Result:
Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.
