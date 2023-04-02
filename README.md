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
## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Procedure
1) Use module projname(input,output) to start the Verilog programmming.
2) Assign inputs and outputs using the word input and output respectively.
3) Use defined keywords like wire,assign and required logic gates to represent the boolean expression.
4) Use each output to represnt onre for differnce and the other for borrow.
5) End the verilog program using keyword endmodule.
## Program:
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by: Mukesh V
RegisterNumber:  212222230086
``` verilog
HALF SUBTRACTOR

module HalfSubtractor(A,B,Diff,Borrow);
input A,B;
output Diff,Borrow;
wire x;
xor (Diff, A,B);
not(x,A);
and(Borrow,x,B);
endmodule
```

``` verilog
FULL SUBTRACTOR

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
## HALF SUBRACTOR
## Logic symbol
![hs1](https://user-images.githubusercontent.com/118707363/229361194-fc3e5646-eba3-4782-948f-0aeb11c09159.png)

## Truthtable
![hs3](https://user-images.githubusercontent.com/118707363/229361263-a00b8f8b-48ca-41ab-942a-b9840295455c.png)



##  RTL realization
![hs2](https://user-images.githubusercontent.com/118707363/229361273-94d50333-53e4-41f7-8ff2-5626878b59c0.png)


## Timing diagram 
![hs4](https://user-images.githubusercontent.com/118707363/229361288-14ed5927-6f94-406e-9478-c55fa31dd218.png)

## FULL SUBRACTOR
## Logic symbol
![fs1](https://user-images.githubusercontent.com/118707363/229361305-54676ec8-da35-4ab1-a3aa-039cc76ad912.png)

## Truthtable

![fs3](https://user-images.githubusercontent.com/118707363/229361308-9b7674b4-dddd-4ad2-a257-181dac962d32.png)


##  RTL realization

![fs2](https://user-images.githubusercontent.com/118707363/229361313-6a195ca2-e5e3-42b6-9d94-ae4acf8e0dce.png)

## Timing diagram 
![fs4](https://user-images.githubusercontent.com/118707363/229361320-16e44614-6c04-4480-9ad8-ad97995d2185.png)

## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
