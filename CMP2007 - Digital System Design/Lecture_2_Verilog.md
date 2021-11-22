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

**Structural Model - XOR example**

![](https://snipboard.io/VfQxI8.jpg)

```c
module (a,b,output);
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