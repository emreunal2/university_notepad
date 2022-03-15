# Week 4:Relational Algebra (Part II)

## Additional Operations

* Set intersection
* Natural join
* Division
* Assignment
* All above other than **aggregation**, can be expressed using basic operations we have seen earlier

## 1. Set-Intersection Operation (kesisim kume)
![](https://snipboard.io/PdWCTF.jpg)

### Set Intersection Operation Example
![](https://snipboard.io/lV9HMN.jpg)

## 2. Natural-Join Operation
![](https://snipboard.io/Cdpa0b.jpg)

### Natural-Join Operation Example
![](https://snipboard.io/J9OGYS.jpg)

## 3. Division Operation
![](https://snipboard.io/Cdpa0b.jpg)

### Division Operation Example
![](https://snipboard.io/P912dC.jpg)
![](https://snipboard.io/Z7XLUP.jpg)
![](https://snipboard.io/yNozQI.jpg)

## 4. Assignment Operation
![](https://snipboard.io/Cdpa0b.jpg)

**Do exercies after this part**

## Extended Relational Algebra Operations

* Generalized Projection
* Aggregate Functions
* Outer Join

## 1. Generalized Projection

![](https://snipboard.io/WefRZ1.jpg)

## 2. Aggregate Functions and Operations

![](https://snipboard.io/OM6YN8.jpg)
![](https://snipboard.io/QOoVSc.jpg)
![](https://snipboard.io/01vY56.jpg)

* Result of aggregation does not have a name
    * Can use rename operation to give it a name
    * For convenience, we permit renaming as part of aggregate operation

branch_name g sum(balance) assum_balance (account)

## Outer Join
* An extension of the join operation that avoids loss of information.
* Computes the join and then adds tuples form one relation that does not match tuples in the other relation to the result of the join. 
* Uses nullvalues:
  * null signifies that the value is unknown or does not exist 
  * All comparisons involving nullare (roughly speaking) falseby definition.
    * We shall study precise meaning of comparisons with nulls later

![](https://snipboard.io/0vRU3V.jpg)
![](https://snipboard.io/oHVDPS.jpg)
![](https://snipboard.io/T5067S.jpg)

## Null Values

* It is possible for tuples to have a null value, denoted by null, for some of their attributes
* `null` signifies an unknown value or that a value does not exist.
* The result of any arithmetic expression involving nullis null.
* Aggregate functions simply ignore null values (as in SQL)
* For duplicate elimination and grouping, null is treated like any other value, and two nulls are assumed to be  the same (as in SQL)
* Comparisons with null values return the special truth value: unknown
  * If falsewas used instead of unknown, then `not` (A < 5) would not be equivalent to **A >= 5**  
* Three-valued logic using the truth value unknown
```SQL
OR: (unknown or true) = true,
    (unknown or false) = unknown
    (unknown or unknown) = unknown
```

```SQL
AND:(true and unknown) = unknown,
    (false and unknown) = false,
    (unknown and unknown) = unknown
```

```SQL
NOT:  (notunknown)= unknown
```
