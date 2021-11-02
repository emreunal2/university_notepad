# Lecture Notes 2Asymptotic Notation

## Theoretical analysis of time efficiency

- Time efficiency is analyzed by determining the number of repetitions of the **basic operation** as a function of **input size**
- **Basic operation**: the operation that contributes most towards the running time of the algorithm

**T(n)≈copC(n)**  
n=input size
T=running time
Cop=Execution time for basic operation
C(n)=Number of times basic operation is executed

| **Problem**                              | **Input size measure**                        | **Basic Operation**           |
| ---------------------------------------- | --------------------------------------------- | ----------------------------- |
| Searching for key in a list of _n_ items | Number of lists items, i.e _n_                | Key comparison                |
| Multiplication of two matrices           | Matrix dimensions or total number of elements | Multiplication of two numbers |
|Checking primalityof a given integer n|n’size= number of digits| Division

