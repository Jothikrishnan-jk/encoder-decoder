### Ex. No. 8
### Date: 9.6.23
# Implementation of Decoder and Encoder using Verilog HDL
## Aim :
To design and implement 3 X 8 decoder and 8 X 3 encoder circuit using Verilog HDL and verify its truth table.
## Components Required:
1.	Laptop with Quartus software and modelsim software.
## Theory:
### Decoder:
The combinational circuit that changes the binary information into 2N output lines is known as Decoders. The binary information is passed in the form of N input lines. The output lines define the 2N-bit code for the binary information.  A 3 to 8 decoder has three inputs (A, B, C) and eight outputs (D0 to D7). Based on the 3 inputs one of the eight outputs is selected.

#### Truth Table
 ![image](https://github.com/rvinifa/encoder-decoder/assets/133735746/2257bde8-88cc-4265-a125-acf6e1fc6db2)

#### Logic Diagram
 ![image](https://github.com/rvinifa/encoder-decoder/assets/133735746/07fde8c3-e974-4f35-b64e-9dac9ae58d83)

#### Block diagram
 ![image](https://github.com/rvinifa/encoder-decoder/assets/133735746/f5e8e12f-cd85-4445-b89d-15584766c1ea)

### Encoder:
The combinational circuits that change the binary information into N output lines are known as Encoders. The binary information is passed in the form of 2N input lines. Encoder performs the reverse operation of the Decoder. The output lines of a digital encoder generate the binary equivalent of the input line whose value is equal to “1” and are available to encode either a decimal or hexadecimal input pattern to typically a binary or “B.C.D” (binary coded decimal) output code. One of the main disadvantages of standard digital encoders is that they can generate the wrong output code when there is more than one input present at logic level “1”.
#### Truth Table
 ![image](https://github.com/rvinifa/encoder-decoder/assets/133735746/c28cf092-f133-4204-8053-8f3284176aec)

A2 = Y7 + Y6 + Y5 + Y4 <br>
A1 = Y7 + Y6 + Y3 + Y2 <br>
A0 = Y7 + Y5 + Y3 + Y1 <br>
#### Logic Diagram
 ![image](https://github.com/rvinifa/encoder-decoder/assets/133735746/1d98c529-816c-48c0-819f-9a3d27265a6b)



#### Block diagram
 ![image](https://github.com/rvinifa/encoder-decoder/assets/133735746/29c3ce25-5337-4f2c-ae30-6ebfbd9ed67a)


## Procedure:
1.	Type the program in Quartus software.
2.	Compile and run the program.
3.	Generate the RTL schematic and save the logic diagram.
4.	Create nodes for inputs and outputs to generate the timing diagram.
5.	For different input combinations, generate the timing diagram.


## Program:
Decoder
```
module decoder(a,b,c,d0,d1,d2,d3,d4,d5,d6,d7);
input a,b,c;
output d0,d1,d2,d3,d4,d5,d6,d7;
assign d0=((~a)&(~b)&(~c));
assign d1=((~a)&(~b)&c);
assign d2=((~a)&b&(~c));
assign d3=((~a)&b&c);
assign d4=(a&(~b)&(~c));
assign d5=(a&(~b)&c);
assign d6=(a&b&(~c));
assign d7=(a&b&c);
endmodule
```

Encoder
```
module encoder(y0,y1,y2,y3,y4,y5,y6,y7,a0,a1,a2);
input y0,y1,y2,y3,y4,y5,y6,y7;
output a0,a1,a2;
assign a0=(y7|y5|y3|y1);
assign a1=(y7|y6|y3|y2);
assign a2=(y7|y6|y5|y4);
endmodule
```

## RTL Schematic:
<img width="342" alt="decoder rtl" src="https://github.com/Jothikrishnan-jk/encoder-decoder/assets/129312867/6a56dbc2-2075-4b4b-b7fe-4f0045bfd011">


<img width="328" alt="encoder rtl" src="https://github.com/Jothikrishnan-jk/encoder-decoder/assets/129312867/2d3cb291-5616-4736-8368-51c5faffadf1">



## Timing Diagram:
<img width="671" alt="decoder wave" src="https://github.com/Jothikrishnan-jk/encoder-decoder/assets/129312867/2217191c-2c3f-4d48-9670-11651be77525">

<img width="626" alt="encoder wave form" src="https://github.com/Jothikrishnan-jk/encoder-decoder/assets/129312867/107c966b-5409-4d9f-ab37-a18e15b73f0c">


## Result:
Thus the decoder and encoder circuits are designed and implemented and the truth tables are verified.
