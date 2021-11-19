# Week 3: Relational Modeland Relational Algebra (Part I)

## Relational Model

* Structure of Relational Databases
* Fundamental Relational-Algebra-Operations
* Additional Relational-Algebra-Operations
* Extended Relational-Algebra-Operations
* Null Values
* Modification of the Database

**Example of a Relation**

![](https://prepinsta.com/wp-content/uploads/2021/04/relationalModel.webp)

### Attribute Types

* Each attribute of a relation has a name
* The set of allowed values for each attribute is called the domainof the attribute
* Attribute values are (normally) required to be atomic; that is, indivisible
* E.g. the value of an attribute can be an account number, but cannot be a set of account numbers
* Domain is said to be atomic if all its members are atomic
* The special value nullis a member of every domain
* The null value causes complications in the definition of many operations
* We shall ignore the effect of null values in our main presentation and consider their effect later

![](https://snipboard.io/5mATV6.jpg)

![](https://snipboard.io/xQsUdF.jpg)

## Keys

* Let K R
* K is a superkey of Rif values for Kare sufficient to identify a unique tuple of each possible relation r(R)
  * by “possibler ” we mean a relation r that could exist in the enterprise we are modeling.
  * Example: ```{customer_name, customer_street}``` and ```{customer_name}``` are both superkeys of Customer, if no two customers can possibly have the same name
  * **In real life, an attribute such as customer_idwould be used instead of customer_name to uniquely identify customers, but we omit it to keep our examples small, and instead assume customer names are unique.**

* **K** is a ```candidate key``` if Kis minimal
* Example: ```{customer_name}``` is a candidate key for Customer, since it is a superkey and no subset of it is a superkey.
* ```Primary key```: a candidate key chosen as the principal means of identifying tuples within a relation
  * Should choose an attribute whose value never, or very rarely, changes.
  * E.g. email address is unique, but may change

### Foreign Keys

* A relation schema may have an attribute that corresponds to the primary key of another relation.  The attribute is called a ```foreign key```.
  *  E.g. `customer_name` and `account_number` attributes of depositorare foreign keys to customerand accountrespectively.
  *  Only values occurring in the primary key attribute of the **referenced relation** may occur in the foreign key attribute of the **referencing relation**.
![](https://snipboard.io/oUvWfe.jpg)
![](https://snipboard.io/5ziP0Q.jpg)
![](https://snipboard.io/VepL9I.jpg)


### Query Languages
* Language in which user requests information from the database.
* Categories of languages
  * Procedural
  * Non-procedural, or declarative
* “Pure” languages:
  * Relational algebra
  * Tuple relational calculus
  * Domain relational calculus
  * Pure languages form underlying basis of query languages that people use.

## Relational Algebra
* Procedural language
* Six Basic Operators:  
![](https://snipboard.io/7fdJob.jpg)

## 1. **Select Operation**

![](https://snipboard.io/bysRZB.jpg)

### Select Operation Example

![](https://snipboard.io/etQINO.jpg)

## 2. **Project Operation**

![](https://snipboard.io/WjSh4A.jpg)

### Project Operation Example

![](https://snipboard.io/jIaCvm.jpg)

