## EX-02 BOOLEAN_FUNCTION_MINIMIZATION
## DATE:05-10-2024
**AIM:**

To implement the given logic function verify its operation in Quartus using Verilog programming.

F1= A’B’C’D’+AC’D’+B’CD’+A’BCD+BC’D 

F2=xy’z+x’y’z+w’xy+wx’y+wxy

**Equipment Required:**

Hardware – PCs, Cyclone II , USB flasher

**Software – Quartus prime**

**Theory**
Boolean Function Minimization is the process of reducing a Boolean expression to its simplest form without changing its functionality. This minimization reduces the number of gates and inputs required, optimizing circuit design.

Logic Gates: Fundamental building blocks like AND, OR, and NOT gates are used to implement Boolean expressions. Karnaugh Map (K-map): A graphical technique for minimizing Boolean expressions by grouping terms based on commonalities. The given Boolean functions can be minimized as follows:

F1 = A’B’C’D’ + AC’D’ + B’CD’ + A’BCD + BC’D The terms can be simplified using K-map techniques to reduce the complexity of the circuit. F2 = xy’z + x’y’z + w’xy + wx’y + wxy Similar simplification can be done for this function to reduce the gate count. The resulting minimized expressions are implemented using Verilog HDL and simulated on the Quartus Prime tool. The outputs can then be verified on an FPGA board (e.g., Cyclone II).

**Logic Diagram**

![image](https://github.com/user-attachments/assets/48876297-ec0d-4930-a015-a45a2b4d7f5b)

**Truth table**

![image](https://github.com/user-attachments/assets/827e5b28-c121-41b8-8712-2a98b419ab0a)

**Procedure**

1.	Type the program in Quartus software.

2.	Compile and run the program.

3.	Generate the RTL schematic and save the logic diagram.

4.	Create nodes for inputs and outputs to generate the timing diagram.

5.	For different input combinations generate the timing diagram.


**Program:**
~~~
 module boolean_function_minimization(a, b, c, d, w, x, y, z, f1, f2);
 input a, b, c, d, w, x, y, z;
 output f1, f2;
 wire x1, x2, x3, x4, x5, x6, x7, x8, x9, x10;
 assign x1 = (~a) & (~b) & (~c) & (~d);
 assign x2 = (a) & (~c) & (~d);
 assign x3 = (~b) & (c) & (~d);
 assign x4 = (~a) & (b) & (c) & (d);
 assign x5 = (b) & (~c) & (d);
 assign f1 = x1 | x2 | x3 | x4 | x5;
 assign x6 = (x) & (~y) & (z);
 assign x7 = (~x) & (~y) & (z);
 assign x8 = (~w) & (x) & (y);
 assign x9 = (w) & (~x) & (y);
 assign x10 = (w) & (x) & (y);
 assign f2 = x6 | x7 | x8 | x9 | x10;
 endmodule
~~~
/* Program to implement the given logic function and to verify its operations in quartus using Verilog programming. 

## Developed by:PRIYADHARSHINI P
## RegisterNumber:24901256


**RTL realization**
![Screenshot 2024-12-28 140754](https://github.com/user-attachments/assets/df4d4bb8-a9ba-4980-af11-f1e9d7b6455f)


**Output:**
![image](https://github.com/user-attachments/assets/940089a4-1926-4343-80be-f583aafc9c4a)

**RTL**
![image](https://github.com/user-attachments/assets/60a067e0-ec89-4c25-98d2-016430b9b9ee)

**Timing Diagram**
![image](https://github.com/user-attachments/assets/65be3b66-3bbd-418d-9eda-84b04916cfef)

**Result:**

Thus the given logic functions are implemented using and their operations are verified using Verilog programming.

