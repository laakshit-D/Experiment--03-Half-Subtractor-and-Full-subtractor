# Experiment--03-Half-Subtractor-and-Full-subtractor
## Implementation-of-Half-subtractor-and-Full-subtractor-circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
Hardware – PCs, Cyclone II , USB flasher
Software – Quartus prime
## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## Half Subtractor Full Subtractor
## Half Subtractor:
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.

![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)

Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

## Full Subtractor:
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Procedure:
1. Use module projname(input,output) to start the Verilog programmming.
2. Assign inputs and outputs using the word input and output respectively.
3. Use defined keywords like wire,assign and required logic gates to represent the boolean expression.
4. Use each output to represnt onre for differnce and the other for borrow.
5. End the verilog program using keyword endmodule

## Program:
```
/*
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by: Laakshit D
RegisterNumber: 212222230071
*/
Half Subtractor
module halfsub(A,B,Diff,Borrow);
input A,B;
output Diff,Borrow;
wire x;
xor (Diff, A,B);
not(x,A);
and(Borrow,x,B);
endmodule

Full Subtractor
module FullSubtractor(A,B,C,Diff,Borrow);
input A,B,C;
output Diff,Borrow;
wire p;
assign Diff = ((A^B)^C);
not(p,A);
assign Borrow = ((p&B)|(p&C)|(B&C));
endmodule
```
## Output:
## Half Subtractor:
## Truthtable
![hftt](https://user-images.githubusercontent.com/119559976/233273611-3a603c7f-ef69-4682-a9ba-f9e5172dade9.jpg)
##  RTL realization
![Screenshot 2023-04-19 135856](https://user-images.githubusercontent.com/119559976/233274192-f4f77f2d-ff9a-4dd8-94e6-1f5256cd2765.png)
## Timing diagram
![Screenshot 2023-04-19 140000](https://user-images.githubusercontent.com/119559976/233274723-6f3f947c-08c2-4694-a7bd-7cf615a4915f.png)
## Full Subtractor:
## Truthtable
![fstt](https://user-images.githubusercontent.com/119559976/233273733-6f4cacd4-7e2a-4380-a89d-cd295ce6527c.jpg)
##  RTL realization
![Screenshot 2023-04-19 144415](https://user-images.githubusercontent.com/119559976/233274265-360a91d6-e0ec-436a-a905-4a573ddaa12b.png)
## Timing diagram
![Screenshot 2023-04-19 144158](https://user-images.githubusercontent.com/119559976/233274569-b7e52caf-ea3d-48c6-9744-3d3190024c16.png)
## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
