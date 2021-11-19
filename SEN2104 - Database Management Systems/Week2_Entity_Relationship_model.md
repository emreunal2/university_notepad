# Week 2:  Entity-Relationship Model

![](https://beginnersbook.com/wp-content/uploads/2015/04/ER_Diagram_Components.png)

### Modeling

* A databasecan be modeled as:
  * a collection of entities,
  * relationship among entities

* An **entity** is an object that exists and is distinguishable from other objects.
* Entities have attributes
* An **entity set** is a set of entities of the same type that share the same properties.
  * Example: set of all persons, companies, trees, holidays
![](https://www.thestudygenius.com/media/2020/02/Entity-Set-image-2.png)

### Relationship Sets

* A **relationship** is an association among several entities
* A **relationship set** is a mathematical relation among n2 entities, each taken from entity sets
![](https://www.gatevidyalay.com/wp-content/uploads/2018/05/Set-Representation-of-ER-Diagram.png)

### Attributes
* An entity is represented by a set of attributes, that is descriptive properties possessed by all members of an entity set.  
* Example:
``` SQL
customer = (customer_id, customer_name, customer_street, customer_city

loan = (loan_number, amount )
```

* **Domain**–the set of permitted values for each attribute
* Attribute types:
  *  Simple and composite attributes.
  *  Single-valuedand multi-valued attributes.
* Derived attributes

![](https://slideplayer.com/slide/6622410/23/images/4/Example+of+a+composite+attribute.jpg)

## Mapping Cardinality Constraints

* Express the number of entities to which another entity can be associated via a relationship set. 
* Most useful in describing binary relationship sets.
* For a binary relationship set the mapping cardinality must be one of the following types:

* **One to one**
* **One to many**
* **Many to one**
* **Many to many**

![](https://www.atnyla.com/library/images-tutorials/tutorial-993242808-cardinality-and-constraints-dbms.jpg)

### Keys 

* A super **key** of an entity set is a set of one or more attributes whose values uniquely determine each entity.
* A **candidate key** of an entity set is a minimal super key
  * ```customer_id``` is candidate key of customer
  * ```account_number``` is candidate key of account
  * Although several candidate keys may exist, one of the candidate keys is selected to be the ```primary key```.
  
### ER Diagrams
![](https://upload.wikimedia.org/wikipedia/commons/7/72/ER_Diagram_MMORPG.png)

* Rectangles represent entity sets.
* Diamonds represent relationship sets.
* Lines link attributes to entity sets and entity sets to relationship sets.
* Ellipses represent attributes
  * Double ellipses represent multivalued attributes.
  * Dashed ellipses denote derived attributes.
* Underline indicates primary key attributes (will study later)

### One to Many Relationship

* In a one-to-many relationship, a loan is associated with at most one customer via borrower, a customer is associated with several (including 0) loans via *borrower*

![](https://fmhelp.filemaker.com/help/18/fmp/en/FMP_Help/images/relational.07.04.2.png)

### Many to One Relationships

* In a many-to-one relationship, a loan is associated with several (including 0) customers via borrower, a customer is associated with at most one loan via borrower21

### Many to Many Relationships

* A customer is associated with several (possibly 0) loans via borrower
* A loan is associated with several (possibly 0) customers via borrower

## **IMPORTANT**

After this part of lesson has lots of visual things when you gonna study look into class videos.
