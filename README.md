AIM:
To simulate and synthesis Logic Gates,Adders and Subtractor using Vivado 2023.1

APPARATUS REQUIRED:
Vivado 2023.1

PROCEDURE:
Open Vivado: Launch Xilinx Vivado software on your computer.

Create a New Project: Click on "Create Project" from the welcome page or navigate through "File" > "Project" > "New".

Project Settings: Follow the prompts to set up your project. Specify the project name, location, and select RTL project type.

Add Design Files: Add your Verilog design files to the project. You can do this by right-clicking on "Design Sources" in the Sources window, then selecting "Add Sources". Choose your Verilog files from the file browser.

Specify Simulation Settings: Go to "Simulation" > "Simulation Settings". Choose your simulation language (Verilog in this case) and simulation tool (Vivado Simulator).

Run Simulation: Go to "Flow" > "Run Simulation" > "Run Behavioral Simulation". This will launch the Vivado Simulator and compile your design for simulation.

Set Simulation Time: In the Vivado Simulator window, set the simulation time if it's not set automatically. This determines how long the simulation will run.

Run Simulation: Start the simulation by clicking on the "Run" button in the simulation window.

View Results: After the simulation completes, you can view waveforms, debug signals, and analyze the behavior of your design

Logic Diagram :
![301405876-ee17970c-3ac9-4603-881b-88e2825f41a4](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/160721712/1134a3fe-a376-4056-a631-faef2d3044aa)

Logic Gates: 

Half Adder:
![301406331-0e1ecb96-0c25-4556-832b-aeeedfdfe7b9](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/160721712/31b13f9e-eade-4a2a-afef-147a912fa88d)

Full adder:
![301406527-9bb3964c-438f-469d-a3de-c1cca6f323fb](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/160721712/eb921269-4493-4f45-b95b-c56efb4f906d)

Half Subtractor:
![301406051-731470b7-eb4e-49f8-8bb7-2994052a7184](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/160721712/f2ee9626-02b1-47f4-9552-3b454a9a0fd9)

Full Subtractor:
![301406088-d66f874b-c1f2-44b3-a035-7149b56430c1](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/160721712/58336438-bf1d-459f-8056-5caf7be5dd84)

8 Bit Ripple Carry Adder
![301406117-7385a408-40a5-4203-8050-b72818622d79](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/160721712/ad4b66f5-e494-448f-a809-9bf8881a828c)

HALF ADDER
VERILOG CODE

module half_adder(Sum,carry,a,b);
input a,b;
output Sum,carry;
assign Sum = a ^ b;
assign carry = a & b;
endmodule
<img width="745" alt="328446511-039b61a6-2608-4b32-ab68-0d4e255ffb0c" src="https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/160721712/b48b5887-36e7-4eb9-8775-8801e847ed6a">

OUTPUT: 
<img width="962" alt="328446549-79b8e891-b02c-4166-b67e-6489a60ffadb" src="https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/160721712/62670991-62e2-4e95-8070-1c7d6b9663ad">

HALF SUBTRACTOR
VERILOG CODE:

module half_sub(Diff,Borrow,a,b);
input a,b;
output Diff,Borrow;
wire w1;
not(w1,a);
xor(Diff,a,b);
and(Borrow,b,w1);
endmodule
<img width="826" alt="328446695-c3675959-8a98-455d-9dee-0098efc72527" src="https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/160721712/7eaa5c22-b343-49c5-9822-797eb2620dd4">

OUTPUT: 
<img width="962" alt="328446809-7a0da717-11b7-4cfd-8c3c-9d60464046a2" src="https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/160721712/59c0acb9-2345-48a6-954d-2c794a4f7772">

FULL ADDER
VERILOG CODE:

module fulladder(sum,cout,a,b,c);
input a,b,c;
output sum,cout;
wire w1,w2,w3,w4,w5;
xor x1(w1,a,b);
xor x2(sum,w1,c);
and a1(w2,a,b);
and a2(w3,b,c);
and a3(w4,a,c);
or o1(w5,c1,c2);
or o2(cout,w5,c3);!
endmodule

OUTPUT: 320199228-0f99f497-5145-41cb-971d-0b96a339897b 320199301-19d4ec03-ae75-493d-b998-798c356a1069
<img width="962" alt="328449197-96ffee78-fc09-42fc-ae57-7fc5d7f6188a" src="https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/160721712/3ca41b3b-1a18-4c8e-be5e-a8de118560fc">
<img width="962" alt="328449333-5b8513ce-de50-4859-a270-f971b78d81a3" src="https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/160721712/226b3e4c-31f8-449e-9ba9-0916dd4e5d42">

FULL SUBTRACTOR
VERILOG CODE:

module full_sub(borrow,diff,a,b,c);
output borrow,diff;
input a,b,c;
wire w1,w4,w5,w6;
xor (diff,a,b,c);
not n1(w1,a);
and a1(w4,w1,b);
and a2(w5,w1,c);
and a3(w6,b,c);
or o1(borrow,w4,w5,w6);
endmodule
<img width="692" alt="328449778-0fa504d4-830e-4462-960f-375e507bbc9b" src="https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/160721712/0b784a22-64f8-4172-a5d8-acfc1c3fc3eb">

OUTPUT: 
<img width="962" alt="328449783-d0c079b1-53c8-4487-ad8c-d73c1dc984c8" src="https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/160721712/916c419f-737a-4cd6-90c2-d6dbf348a458">

LOGIC GATES
VERILOG CODE:

module logicgates(a,b,andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate);
input a,b;
output andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate;
and(andgate,a,b);
or(orgate,a,b);
xor(xorgate,a,b);
nand(nandgate,a,b);  
nor(norgate,a,b);
xnor(xnorgate,a,b);
not(notgate,a);
endmodule
<img width="822" alt="328449983-3e0fe74b-128b-4ce5-9880-e787f077aaa0" src="https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/160721712/800914b5-5e84-45e1-bd82-c704ec22c9c3">

OUTPUT: 
<img width="962" alt="328450064-bad14874-6ea4-4791-9af4-f85efb36a5dd" src="https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/160721712/4096d6a1-9b5b-408e-9c96-a157496705fe">

4-BIT RIPPLE CARRY ADDER
VERILOG CODE:

module rippe_adder(S, Cout, X, Y,Cin);
input [3:0] X, Y;
input Cin;
output [3:0] S;
output Cout;
wire w1, w2, w3;
fulladder u1(S[0], w1,X[0], Y[0], Cin);
fulladder u2(S[1], w2,X[1], Y[1], w1);
fulladder u3(S[2], w3,X[2], Y[2], w2);
fulladder u4(S[3], Cout, X[3], Y[3], w3);
endmodule

Output :
<img width="962" alt="328450140-880ef584-fdca-4c2b-bd76-d6705d64062d" src="https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/160721712/128f5941-16f5-4ce2-aaa4-15855bd1c9bf">

<img width="962" alt="328450422-ac214aa7-766a-4660-b9a4-e4f5c8be392b" src="https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/160721712/96f60620-b6dc-4850-9155-52fabe84dbd2">

module fulladder(S, Co, X, Y, Ci);
input X, Y, Ci;
output S, Co;
wire w1,w2,w3;
xor G1(w1, X, Y);
xor G2(S, w1, Ci);
and G3(w2, w1, Ci);
and G4(w3, X, Y);
or G5(Co, w2, w3);
endmodule
OUTPUT: 
<img width="962" alt="328450422-ac214aa7-766a-4660-b9a4-e4f5c8be392b" src="https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/160721712/ab379354-642c-43c5-8f18-f230dfd69d95">

8-BIT RIPPLE CARRY ADDER
VERILOG CODE:

module rippe_adder(S, Cout, X, Y,Cin);
input [7:0] X, Y;// Two 4-bit inputs
input Cin;
output [7:0] S;
output Cout;
wire w1, w2, w3, w4, w5, w6, w7;
 // instantiating 8 1-bit full adders in Verilog
fulladder u1(S[0], w1,X[0], Y[0], Cin);
fulladder u2(S[1], w2,X[1], Y[1], w1);
fulladder u3(S[2], w3,X[2], Y[2], w2);
fulladder u4(S[3], w4,X[3], Y[3], w3);
fulladder u5(S[4], w5,X[4], Y[4], w4);
fulladder u6(S[5], w6,X[5], Y[5], w5);
fulladder u7(S[6], w7,X[6], Y[6], w6);
fulladder u8(S[7], Cout,X[7], Y[7], w7);
endmodule
module fulladder(S, Co, X, Y, Ci);
input X, Y, Ci;
output S, Co;
wire w1,w2,w3;
  //Structural code for one bit full adder
xor G1(w1, X, Y);
xor G2(S, w1, Ci);
and G3(w2, w1, Ci);
and G4(w3, X, Y);
or G5(Co, w2, w3);
endmodule
OUTPUT:

RESULT: THUS THE LOGIC GATES,ADDERS,SUBTRACTORS VERILOG CODE IS SIMULATED USING VIVADO 2023.1 AND OUTPUT VERIFIED SUCCESSFULLY
