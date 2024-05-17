# SIMULATION AND IMPLEMENTATION OF LOGIC GATES, ADDERS, AND SUBTRACTOR
# AIM:

   To simulate and synthesis Logic Gates,Adders and Subtractor using vivado 2023.2.

# APPARATUS REQUIRED:

   Vivado 2023.2

# PROCEDURE:

STEP:1 Start the vivado software, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and module name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the run simulation adn then run Behavioral Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

STEP:7 compare the output with truth table

# Logic Diagram :

# Logic Gates:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/ee17970c-3ac9-4603-881b-88e2825f41a4)

# VERILOG CODE:

module logicgates(a,b,andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate);

input a,b;

output andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate;

and(andgate,a,b);

or(orgate,a,b);

xor(xorgate,a,b);

nand(nandgate,a,b);

nor(norgate,a,b);

xnor(xnorgate,a,b);

not(norgate,a,b);

endmodule

# Output

![logic gates](https://github.com/riyamicheal/VLSI-LAB-EXP-1/assets/124061774/51068f9d-91a4-4a83-8c93-a04de6a5d24d)


# Half Adder:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/0e1ecb96-0c25-4556-832b-aeeedfdfe7b9)

# Verilog code

module HA(a,b,sum,carry);

input a,b;

output sum,carry;

xor g1(sum,a,b);

and g2(carry,a,b);

endmodule

# Output

![half adder](https://github.com/riyamicheal/VLSI-LAB-EXP-1/assets/124061774/284eb1d3-4b50-40c6-8d64-50f09f5cc0cc)


# Full adder:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/9bb3964c-438f-469d-a3de-c1cca6f323fb)

# Verilog code

module FA(a,b,cin,sum,cout);

input a,b,cin;

output sum,cout;

wire w1,w2,w3;

xor g1(w1,a,b);

and g2(w2,w1,cin);

and g3(w3,a,b);

xor g4(sum,w1,cin);

or g5(cout,w2,w3);

endmodule

# Output:

![fULL ADDER](https://github.com/riyamicheal/VLSI-LAB-EXP-1/assets/124061774/94eb067e-ff6f-49fa-b91c-7dba1751b741)


# Half Subtractor:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/731470b7-eb4e-49f8-8bb7-2994052a7184)

# Verilog code

module HS(a,b,difference,borrow);

input a,b;

output difference,borrow;

wire w1;

xor g1(difference,a,b);

not g2(w1,a);

and g3(borrow,w1,b);

endmodule

# Output:

![hs](https://github.com/riyamicheal/VLSI-LAB-EXP-1/assets/124061774/df2d81c5-54ed-4a7f-a4d6-9323dcb09ad4)

# Full Subtractor:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/d66f874b-c1f2-44b3-a035-7149b56430c1)

# Verilog code

module FS(a,b,bin,difference,bout);

input a,b,bin;

output difference,bout;

wire w1,w2,w3,w4,w5;

xor g1(w1,a,b);

not g2(w2,a);

xor g3(difference,w1,bin);

not g4(w3,w1);

and g5(w4,w3,bin);

and g6(w5,w2,b);

or g7(bout,w4,w5);

endmodule

# Output:

![Full subtractor](https://github.com/riyamicheal/VLSI-LAB-EXP-1/assets/124061774/e63cff69-93d7-48fb-b1b5-07c3ab123d9e)


# 8 Bit Ripple Carry Adder

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/7385a408-40a5-4203-8050-b72818622d79)

# Verilog code

module fa(a,b,c,sum,carry);

input a,b,c;

output sum,carry;

assign sum = a^b^c;

assign carry=(a&b)|(b&c)|(c&a);

endmodule

module rca(a,b,cin,sum,cout);

input [7:0]a,b;

input cin;

output [7:0]sum;

output cout;

wire c1,c2,c3,c4,c5,c6,c7;

fa fa1(a[0],b[0],cin,sum[0],c1);

fa fa2(a[1],b[1],c1,sum[1],c2);

fa fa3(a[2],b[2],c2,sum[2],c3);

fa fa4(a[3],b[3],c3,sum[3],c4);

fa fa5(a[4],b[4],c4,sum[4],c5);

fa fa6(a[5],b[5],c5,sum[5],c6);

fa fa7(a[6],b[6],c6,sum[6],c7);

fa fa8(a[7],b[7],c7,sum[7],cout);

endmodule

# Output:

![rca](https://github.com/riyamicheal/VLSI-LAB-EXP-1/assets/124061774/4b518955-0312-44e4-b953-e8fdea5c6dcd)


# RESULT:

Thus the simulation and synthesis of Logic Gates,Adders and Subtractors using vivado has been sucessfully executed and verified .

