### Exercise-07-Multiplexer-and-De-multiplexer
## NAME: Shaik Samreen
## REGISTER NUMBER: 23013412
### AIM:
To implement 4 X1 multiplexer and 1X4 de multiplexer using verilog and validate its outputs
### HARDWARE REQUIRED:
– PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:
Quartus prime
### THEORY 

## What are Multiplexer and Demultiplexer?
In-network transmission, both the multiplexer and demultiplexer are combinational circuits. A multiplexer selects an input from several inputs then it is transmitted in the form of a single line. An alternative name of the multiplexer is MUX or data selector. A demultiplexer uses one input signal and generates many. So it is known as Demux or data distributor.

## What is a Multiplexer?
The multiplexer is a device that has multiple inputs and single line output. The select lines determine which input is connected to the output, and also increase the amount of data that can be sent over a network within a certain time. It is also called a data selector.

The single-pole multi-position switch is a simple example of a non-electronic circuit of the multiplexer, and it is widely used in many electronic circuits. The multiplexer is used to perform high-speed switching and is constructed by electronic components.

![image](https://user-images.githubusercontent.com/36288975/170912485-73c395c7-23c0-4e78-a53d-a2f0d07d9662.png)
          Figure-01 multiplexer block diagram 

Multiplexers are capable of handling both analog and digital applications. In analog applications, multiplexers are made up of relays and transistor switches, whereas in digital applications, the multiplexers are built from standard logic gates. When the multiplexer is used for digital applications, it is called a digital multiplexer.

4-to-1 Multiplexer
The 4X1 multiplexer comprises 4-input bits, 1- output bit, and 2- control bits. The four input bits are namely 0, D1, D2, and D3, respectively; only one of the input bits is transmitted to the output. The o/p ‘q’ depends on the value of control input AB. The control bit AB decides which of the i/p data bit should transmit the output. The following figure shows the 4X1 multiplexer circuit diagram using AND gates. For example, when the control bits AB =00, then the higher AND gates are allowed while remaining AND gates are restricted. Thus, data input D0 is transmitted to the output ‘q”
![image](https://user-images.githubusercontent.com/36288975/170912568-3598c60a-5035-41f3-b0c4-ccedba13aca5.png)


Figure2 4X1 multiplexer 
If the control input is changed to 11, then all gates are restricted except the bottom AND gate. In this case, D3 is transmitted to the output, and q=D0. If the control input is changed to AB =11, all gates are disabled except the bottom AND gate. In this case, D3 is transmitted to the output, and q = D3. The best example of a 4X1 multiplexer is IC 74153. In this IC, the o/p is the same as the i/p. Another example of a 4X1 multiplexer is IC 45352. In this IC, the o/p is the compliment of the i/p


## What is Demultiplexer?
De-multiplexer is also a device with one input and multiple output lines. It is used to send a signal to one of the many devices. The main difference between a multiplexer and a de-multiplexer is that a multiplexer takes two or more signals and encodes them on a wire, whereas a de-multiplexer does reverse to what the multiplexer does.
![image](https://user-images.githubusercontent.com/36288975/170912606-a30e4b74-1726-4430-b245-2c3c3d9c232d.png)
Figure 3 De-multiplexer 
1-4 Demultiplexer
The 1-to-4 demultiplexer comprises 1- input bit, 4-output bits, and control bits. The 1X4 demultiplexer circuit diagram is shown below.![image](https://user-images.githubusercontent.com/36288975/170912683-00fb746a-1d45-4023-91d1-3a70b841073c.png)

![image](https://user-images.githubusercontent.com/36288975/170912741-7cbd52af-7e0d-4be3-b5c6-6fb9c4eca7c9.png)

Figure4 1X4 De-multiplexer 
The i/p bit is considered as Data D. This data bit is transmitted to the data bit of the o/p lines, which depends on the AB value and the control i/p.

When the control i/p AB = 01, the upper second AND gate is permitted while the remaining AND gates are restricted. Thus, only data bit D is transmitted to the output, and Y1 = Data.

If the data bit D is low, the output Y1 is low. IF data bit D is high, the output Y1 is high. The value of the output Y1 depends upon the value of data bit D, the remaining outputs are in a low state.

If the control input changes to AB = 10, then all the gates are restricted except the third AND gate from the top. Then, data bit D is transmitted only to the output Y2; and, Y2 = Data. . The best example of 1X4 demultiplexer is IC 74155.

 
 
### Procedure

1. Start the module using module projname().
2. Declare the inputs and outputs along with the select lines according to the multiplexer and demultiplexer.
3. Use wire to assign intermediate outputs.
4. Use and,or and not gates to get the desired output.
5. End the module.
6. Generate RTL realization and timing diagrams.


### PROGRAM 
## 4x1 Multiplexer:
```
   module MUX(I0,I1,I2,I3,S0,S1,Y);
   input I0,I1,I2,I3,S0,S1;
   output Y;
   wire S0C,S1C;
   not(S0C,S0);
   not(S1C,S1);
   wire P,Q,R,S;
   and(P,S0C,S1C,I0);
   and(Q,S0C,S1,I1);
   and(R,S0,S1C,I2);
   and(S,S0,S1,I3);
   or(Y,P,Q,R,S);
   endmodule
```
## 1x4 De-Multiplexer:
```
   module DEMUX(Y0,Y1,Y2,Y3,S0,S1,I);
   input S0,S1,I;
   output Y0,Y1,Y2,Y3;
   wire S0C,S1C;
   not(S0C,S0);
   not(S1C,S1);
   and(Y0,I,S0C,S1C);
   and(Y1,I,S0C,S1);
   and(Y2,I,S0,S1C);
   and(Y3,I,S0,S1);
   endmodule
```
### OUTPUT:

## RTL LOGIC :

 ## 4X1 Multiplexer

![171004630-2a2e7fda-b3d6-4968-a9bc-3585b05167a5](https://github.com/samreen-sk/Exercise-07-Multiplexer-and-De-multiplexer/assets/149347632/a4020de4-3ffa-463c-9572-e5d37b0be4ef)

## 1x4 Multiplexer:

![171004850-b6d29cd4-d0bd-4ae9-9c2a-475c70fea0f5](https://github.com/samreen-sk/Exercise-07-Multiplexer-and-De-multiplexer/assets/149347632/a05f4983-98b7-435c-a4fc-4781777a36ea)


### TIMING DIGRAMS  

## 4x1 Multiplexer:

![171004670-c318ea92-5b2a-4548-bec4-cfda8678233c](https://github.com/samreen-sk/Exercise-07-Multiplexer-and-De-multiplexer/assets/149347632/e3c82674-5d24-43df-b417-8fc2ff4c2094)

![171004680-615d2832-fe01-4d18-b31c-97840ef99170](https://github.com/samreen-sk/Exercise-07-Multiplexer-and-De-multiplexer/assets/149347632/b5240bee-409b-43da-a595-39f42662e4e6)


![171004692-1787942f-2a73-4249-9b2d-31daa4cfcd05](https://github.com/samreen-sk/Exercise-07-Multiplexer-and-De-multiplexer/assets/149347632/c7f55b82-667c-4baa-a736-0ec348b59503)

![171004694-334a82ff-ecd4-443d-802b-981789c8f0d1](https://github.com/samreen-sk/Exercise-07-Multiplexer-and-De-multiplexer/assets/149347632/ad0726e6-f255-48e2-a0c2-3ad0bf3f3561)

## 1x4 Multiplexer:

![171004916-1d2a0998-476a-4968-bb90-c8cc1224233d](https://github.com/samreen-sk/Exercise-07-Multiplexer-and-De-multiplexer/assets/149347632/8a10696e-0648-48f4-b6a5-9d0908e8a156)


### TRUTH TABLE 

## 4x1 Multiplexer:

![171004716-8451ff45-1cce-49b6-a6ce-7a39e7371cc1](https://github.com/samreen-sk/Exercise-07-Multiplexer-and-De-multiplexer/assets/149347632/f7f46c60-0e44-4aa3-a759-7a86cea5590d)

## 1x4 Multiplexer:

![171004968-2bda1a57-cead-4a56-b27e-09b21013fcdf](https://github.com/samreen-sk/Exercise-07-Multiplexer-and-De-multiplexer/assets/149347632/7a56c695-9923-434d-be72-9b1280da712c)


### RESULT:
Hence 4x1 Multiplexer and 1x4 Demultiplexer is been implemented and verified using verilog programming and its output are validated.

