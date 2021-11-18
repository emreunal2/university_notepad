# Database Management System

- DBMS contains information about a particular enterprise

  - Collection of interrelated data
  - Set of programs to access the data
  - An environment that is both convenient and efficient to use

- Database Applications:

  - Banking: transactions
  - Airlines: reservations, schedules
  - Universities: registration, grades
  - Sales: customers, products, purchases
  - Online retailers: order tracking, customized recommendations
  - Manufacturing: production, inventory, orders, supply chain
  - Human resources: employee records, salaries, tax deductions

- Databases can be very large.
- Databases touch all aspects of our lives

## University Database Example

- Application program examples:
  - Add new students, instructors, and courses
  - Register students for courses, and generate class rosters
  - Assign grades to students, compute grade point averages (GPA) and generate transcripts
-

## Relational Model

- All the data is stored in various tables.
- Example of tabular data in the relational model

![](https://binaryterms.com/wp-content/uploads/2019/11/Student-Relational-Model-diagram.jpg)

## A Sample Relational Database

![](https://www.researchgate.net/profile/Dhanasekar-Vimal-Kumar/publication/264823200/figure/fig1/AS:823629063393280@1573379879885/Multi-relational-database-an-example.png)

## Database Design

- **Logical Design** –Deciding on the database schema. Database design requires that we find a “good” collection of relation schemas.
  - Business decision –What attributes should we record in the database?
  - Computer Science decision –What relation schemas should we have and how should the attributes be distributed among the various relation schemas?
- **Physical Design** –Deciding on the physical layout of the database

### Design Approaches

Need to come up with a methodology to ensure that each of the relations in the database is “good”, two ways of doing so:

- **Entity Relationship Mode**

  - Models an enterprise as a collection of entities and relationships
  - Represented diagrammatically by an entity-relationship diagram:

- Normalization Theory

## Data Definition Language (DDL)

Specification notation for defining the database schema example:

```SQL
create table instructor(
    ID  char(5),
    user_name    varchar(20),
    dept_name  varchar(20),
    salary  numeric(8,2))
```

- DDL compiler generates a set of table templates stored in a data dictionary
- Data dictionary contains metadata (i.e., data about data)
  - Database schema
  - Integrity constraints(Primary Key)
  - Authorization

## Data Manipulation Language (DML)

DML also known as query language  
**Two classes of languages:**

- **Pure** used for proving properties about computational power and for optimization

  - Relational Algebra
  - Tuple relational calculus
  - Domain relational calculus

- **Commercial**–used in commercial systems:
  - SQL is the most widely used commercial language

## SQL

- The most widely used commercial language
- To be able to compute complex functions SQL is usually embedded in some higher-level language
- Application programs generally access databases through one of
  - Language extensions to allow embedded SQL
  - Application program interface (e.g., ODBC/JDBC) which allow SQL queries to be sent to a database

## Query Processing

![](https://images.slideplayer.com/38/10811363/slides/slide_2.jpg)