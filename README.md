# Experiment-08- Encoders-and-decoders 
### AIM: To implement 8 to 3 Encoder and  3to8 Decoder using verilog and validate its outputs
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## Encoders
Binary code of N digits can be used to store 2N distinct elements of coded information. This is what encoders and decoders are used for. Encoders convert 2N lines of input into a code of N bits and Decoders decode the N bits into 2N lines.

1. Encoders –
An encoder is a combinational circuit that converts binary information in the form of a 2N input lines into N output lines, which represent N bit code for the input. For simple encoders, it is assumed that only one input line is active at a time.

As an example, let’s consider Octal to Binary encoder. As shown in the following figure, an octal-to-binary encoder takes 8 input lines and generates 3 output lines.

![image](https://user-images.githubusercontent.com/36288975/171543588-bc0746df-a173-4b35-989e-5fb7d385fe8a.png)
## Figure -01 3 to 8 Encoder 


Implementation –

X = D4 + D5 + D6 + D7
Y = D2 +D3 + D6 + D7
Z = D1 + D3 + D5 + D7 
Hence, the encoder can be realised with OR gates as follows:


![image](https://user-images.githubusercontent.com/36288975/171543740-68403b82-aa93-4c98-9343-f32b14885a2e.png)
## Figure -02 3 to 8 Encoder implenentation 

 ### Decoders 
A decoder does the opposite job of an encoder. It is a combinational circuit that converts n lines of input into 2n lines of output.

Let’s take an example of 3-to-8 line decoder.
Implementation –
D0 is high when X = 0, Y = 0 and Z = 0. Hence,

D0 = X’ Y’ Z’ 
Similarly,

D1 = X’ Y’ Z
D2 = X’ Y Z’
D3 = X’ Y Z
D4 = X Y’ Z’
D5 = X Y’ Z
D6 = X Y Z’
D7 = X Y Z 


![image](https://user-images.githubusercontent.com/36288975/171543978-ee2d0671-2846-40a1-8705-507fd6287a49.png)
## Figure -03 8 to 3 Decoder 



![image](https://user-images.githubusercontent.com/36288975/171543866-5a6eace6-8683-49d7-9c4f-a7cb30ec3035.png)
## Figure -04 8 to 3 Decoder implementation 

### Procedure

Step 1: Open Quartus II and select new project and choose the file location.

Step 2: Module Declaration. Module should have the file name.

Step 3: Input-Output Delecaration.

Step 4: Use assign to define the functionality of logic circuits.

Step 5: At the end give endmodule.

Step 6: Run the program and choose RTL viewer to get RTL realization.

Program for Endocers and Decoders and verify its truth table in quartus using Verilog programming



### PROGRAM 
/*
Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.
Developed by: santhana lakshmi.k
RegisterNumber: 22003398 
*/
For Encoder:

module encode(a,b,c,d0,d1,d2,d3,d4,d5,d6,d7);

output a,b,c;

input d0,d1,d2,d3,d4,d5,d6,d7;

or(a,d4,d5,d6,d7);

or(b,d2,d3,d6,d7);

or(c,d1,d3,d5,d7);

endmodule

For Decoder:

module decode(d0,d1,d2,d3,d4,d5,d6,d7,a,b,c);

output d0,d1,d2,d3,d4,d5,d6,d7;

input a,b,c;

assign d0 = (~a&~b&~c);

assign d1 = (~a&~b&c);

assign d2 = (~a&b&~c);

assign d3 = (~a&b&c);

assign d4 = (a&~b&~c);

assign d5 = (a&~b&c);

assign d6 = (a&b&~c);

assign d7 = (a&b&c);

endmodule

### RTL LOGIC  

ENCODER

![214379229-9fcd4af0-2e57-4cd3-88de-b8907bdd8e84](https://user-images.githubusercontent.com/119475762/214640807-2decd58f-009e-49b6-a100-3c7caf698d70.png)

DECODER

![214379328-899a292c-4b95-4f97-9b07-5ceed9bb84b0](https://user-images.githubusercontent.com/119475762/214640896-6a4a5eed-1a7d-4acc-afd8-e0c731521028.png)


### TIMING DIGRAMS  

ENCODER

![214379455-7fd6c6a2-239b-474c-901e-693ff63f103f](https://user-images.githubusercontent.com/119475762/214640999-843f0c61-2eda-42e8-a710-990c6a86c29d.png)

DECODER

![214379903-a226e5e4-9a0c-4ae3-8ce4-41b0821a12f1](https://user-images.githubusercontent.com/119475762/214641100-bab511bf-4b9d-42c3-a50e-4646dbf1f790.png)

### TRUTH TABLE 

Encoder

![214380081-ae919d79-eb91-41a4-a184-1df8ec42b0a7](https://user-images.githubusercontent.com/119475762/214641257-a8af4f6b-aa10-41a1-9598-7759bcdf8c75.png)

DECODER

![214380148-9b05957c-9395-4776-b4b8-e518d61c41eb](https://user-images.githubusercontent.com/119475762/214641340-db9cc65e-61df-4993-8678-d137a3f57880.png)

### RESULTS 
8 to 3 Encoder and 3to8 Decoder has been implemented by using verilog and its outputs are validated
