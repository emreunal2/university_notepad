# Lecture Notes 2 Asymptotic Notation

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
| Checking primalityof a given integer n   | n’size= number of digits                      | Division                      |

## best-case, avarage-case, worst-case

For some algorithms, efficiency depends on form of input:

- Worst case: Cworst(n) –maximum over inputs of size n
- Best case: Cbest(n) –minimum over inputs of size n
- Average case: Cavg(n) –“average” over inputs of size n

**Example:**

```py
while i<n and A[i] not K:
    i=i+1
if i<n return i
else return -1
```

- Worst Case?
- Best Case?
- Average Case?

## **Asymptotic Notation**

- Big O notation or Big Oh notation, and also known as Landau notation or asymptotic notation
- A mathematical notation used to describe the asymptotic behavior of functions
- More precisely, the symbol Ois used to describe an asymptotic upper bound for the magnitude of a function in terms of another, usually simpler, function
- In computer science, useful in the analysis of the complexity of algorithms.

## Simplification

- Big-O notation lets us focus on the big picture.
- When faced with a complicated function like 3n2 + 4n + 5, we just replace it with O(f(n)), where f(n) is as simple as possible.
- In this particular example we’d use O(n2), because the quadratic portion of the sum dominates the rest.

## Simplification Rules

1. Multiplicative constants can be omitted:
   - _14n^2becomes n^2_
1. n^a dominates n^b if a > b: for instance,
   - _n^2 dominates n_
1. Any exponential dominates any polynomial:
   -  3^n dominates n^5(it even dominates 2^n
1. Likewise, any polynomial dominates any logarithm
   *  n dominates (log n)^3

## Common plots of O(T(n))
![test](https://jarednielsen.com/static/140e001aad420b3bcdda52c9da2a01f8/a987b/jarednielsen-big-o-chart.png)



