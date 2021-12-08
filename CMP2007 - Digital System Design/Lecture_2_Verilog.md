# Lecture 3 Verilog

1. Hardware Description Language Overview
2. Verilog Introduction

## 1. Hardware Description Languages

**Basic Idea:**  Language constructs describe circcuits with two basic forms

1. **Structural descriptions**: connections of
components. Nearly one-to-one
correspondence to with schematic diagram.
2. **Behavioral descriptions:** use high-level
constructs (similar to conventional
programming) to describe the circuit
function.
![](https://snipboard.io/LAPtl8.jpg)

### Sample Design Methodology

![](https://snipboard.io/wXZiUf.jpg)

**Verilog:**
* Simple C-like syntax for structural and behavior hardware constructs
* Mature set of commercial tools for synthesis and simulation

**VHDL:**
* Semantically very close to Verilog
* More syntactic overhead
* Extensive type system for “synthesis time” checking

**System Verilog:**
* Enhances Verilog with strong typing along with other additions
* Somewhat less mature tool-flow

**BlueSpec:**
* Invented by Prof. Arvind at MIT
* Originally built within the Haskell programming language
* Now available commercially: bluespec.edu


## 2. Verilog Introduction

* A **module** definition describes a component in a circuit
* Two ways to describe module contents:
- Structural Verilog
    * List of sub-components and how they are connected
    * Just like schematics, but using text
    * You get precise control over circuit details
    * May be necessary to map to special resources of the FPGA/ASIC
- Behavioral Verilog
    * Describe what a component does, not how it does it
    * May be simpler to write than structural description
    * Synthesized into a circuit that has this behavior
    * Result is only as good as the tools
* Build up a hierarchy of modules. Top-level module is your
entire design (or the environment to test your design).
* Common approach is to us behavioral descriptions for
“leaf cells” and structural to build hierarchy.

### Verilog modules and Instantiation:

![](https://snipboard.io/yfd1aF.jpg)
### A. Structural Model
**Structural Model - XOR example**

![](https://snipboard.io/VfQxI8.jpg)

```c
module xor_gate(a,b,output);
    input a,b;
    output output;
    wire aBar, bBar, t1, t2;
    not invA(aBar, a);
    not invB(bBar, b);
    and and1(t1, a, bBar);
    and and2(t2,b aBar);
    or or1(out, t1, t2);
endmodule
```

**Structural Example: 2-to1 mux**
![](https://snipboard.io/IR23vw.jpg)

```c
module mux2(select,in0,in1,out);
    input select,in0,in1;
    output out;
    wire sBar,w1,w2;
    not (sbar, select)
    and (w1,sbar,in0)
    and (w2, select, in1)
    or (out, t1, w2)
endmodule
```
### B. Behavioral Model

**Simple Behavioral Model**
```c
module foo(out,in1,in2);
    input in1, in2;
    output out;
    assign out= in1 & in3;
endmodule
```
* Shorthand for explicit instantiation of “and” gate (in this case).
* The assignment continuously happens, therefore any change on the
rhs is reflected in out immediately (except for the small delay
associated with the implementation of the &).
* Not like an assignment in C that takes place when the program
counter gets to that place in the program.
**Verilog Operators:**  
![](https://snipboard.io/JYSytL.jpg)

**Behavioral Example-Ripple Adder**  

```c
module FullAdder(a,b,ci,r,c0);
    input a,b,ci;
    output r,co;
    assign r=a^b^ci;
    assign co=a&ci | a&b | b & ci;
endmodule
```

```c
module Adder(A, B, R);
input [3:0] A;
input [3:0] B;
output [4:0] R;
wire c1, c2, c3;
FullAdder
add0(.a(A[0]), .b(B[0]), .ci(1’b0), .co(c1),
.co(c2),
.co(c3),
.r(R[0]) ),
.r(R[1]) ),
.r(R[2]) ),
.co(R[4]), .r(R[3]) );
add1(.a(A[1]), .b(B[1]), .ci(c1),
add2(.a(A[2]), .b(B[2]), .ci(c2),
add3(.a(A[3]), .b(B[3]), .ci(c3),
endmodule
```

**Assignment Examples:**

![](https://snipboard.io/wNoT62.jpg)

