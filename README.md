# Experiment--04-Implementation-of-combinational-logic-using-universal-gates
Implementation of combinational logic using universal-gates
 
## AIM:
To implement the given logic function using NAND and NOR gates and to verify its operation in Quartus using Verilog programming.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')' using NAND gate
F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')' using NOR gate
## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime


## Theory
Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output. 

## Using NAND gates
NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate. So its output is complement of the output of an AND gate.This gate can have minimum two inputs, output is always one. By using only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR. So this gate is also called as universal gate. First note that the entire expression is inverted and we have three terms ANDed. This means that we must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression. Finally, negated single terms can be generates with a 2-input NAND gate acting as an inverted.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'

## Logic Diagram

Using NOR gates
NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'

## Logic Diagram
## Procedure
## Program:
~~~
/*
Program to implement the given logic function using NAND and NOR gates and to verify its operations in quartus using Verilog programming.
Developed by: A.sasidharan
RegisterNumber: 212221240049
*/
~~~
~~~
module exp4(a,b,c,d,f);
input a,b,c,d;
output f;
wire p,q,r;
assign p = (~c&~b&~a);
assign q = (~d&~c&~a);
assign r = (c&~(~b)&~a);
assign f= p&~q&~r;
endmodule
~~~
~~~
module exp4(a,b,c,d,n);
input a,b,c,d;
output n;
wire p,q,r,s;
assign p = c&(~b)&a;
assign q = d&(~c)&a;
assign r = c&(~b)&a;
assign s = ~(p|q|r);
not(n,s);
endmodule
~~~
## Output:

## RTL realization:
![image](https://user-images.githubusercontent.com/94154712/192596784-fbc29bf4-6957-4841-972e-66a41809d981.png)
## Timing Diagram:
![image](https://user-images.githubusercontent.com/94154712/192596961-5ae9fc2f-fe07-44f5-b64f-ec340b677dbb.png)
## Truthtable:
![image](https://user-images.githubusercontent.com/94154712/192597057-343f673d-e425-4d5c-9321-9d657502a09a.png)
## RTL realization:
![image](https://user-images.githubusercontent.com/94154712/192598299-26bd2aa5-6914-40d5-911b-ae24d300e622.png)
## Timing Diagram:
![Screenshot (150)](https://user-images.githubusercontent.com/94154712/192599215-87da40ba-15a0-465e-b6d0-bcb2472cc00e.png)

## Truthtable:
![image](https://user-images.githubusercontent.com/94154712/192598562-e8c00af0-8045-42aa-a907-79899bf8fa36.png)
## Result:
Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.
