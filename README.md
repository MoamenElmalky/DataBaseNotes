# Database — ITI Course Notes

*2026-11-17 12:43*

## Day - 1

### Database Life Cycle

* **Analysis -> System Analysis**
  * Scope (Requirement Document)
    * HR System
* **Database Design ->**
  * ERD (Entity Relationship Diagram)
* **Database Mapping**
  * Set of Rules
  * Actual Schema
  * Tables
* **DB Implementation (Shared Database VS Standalone)**
  * Physical Database
  * Tool
  * RDBMS (Relational Database Management System)
    * (SQL Server - Oracle - MySQL - Access)
      * SQL (Structured Query Language)
    * Database Developer
* **Application**
  * GUI -- Interface
  * Website --> Mobile --> Desktop
    * Application Programmer (DB user)
  * MVC, C#, Java, React, JavaScript, PHP

**Client -> End user -> browser -> URL**
Does not deal with the database directly.

---

### File-based System

* **Delimited File**

  Sama,Ahmed,18  
  Youssef,Sanad,20  
  Amin,Ahmed,20  
  Kareem,Hesham,17  
  Omar,Adel,22  

* **Fixed Width File**

  10 (2 chars) java (4 chars) 20 (2 chars) SD (2 chars)  
  30 (2 chars) admin (5 chars) 40 (2 chars) HR (2 chars)  

#### Problems

* Difficult Search.
* Low Performance.
* Separated Copies.
* No Relationship.
* No Database Integrity.
* Data Redundancy.
* Long Development Time.
* Security & Permissions.
* Inconsistency & Redundancy.
* Manual Backup & Restore.
* No Standard.
* Difficult Integration.
* Program-Data Dependence.
* Incompatible File Format.
* Limited Data Sharing.

---

### Database System

* **Tables & Relationships**

| First Name | Last Name | Age | Note |
| :--- | :--- | :--- | :--- |
| Sama | Ahmed | 18 | (can be primary) |
| Youssef | Khaled | 20 | (can be primary) |
| Amin | Ahmed | 21 | (can be primary) |
| Kareem | Hesham | 17 | (can be primary) |
| Omar | Adel | 22 | (can be primary) |
| Kareem | Hesham | 17 | X (Error) |
| NULL | NULL | NULL | (can't be Primary) |

* **Standardization**
* **Metadata ->** Data about data
* **Column**
* **Primary Key** (Unique & Not NULL)
* **Foreign Key** (it relates tables to others)

#### Core Definitions

* **Database Inconsistency:** The same data item has different values in different places.
* **Database:** A collection of related data.
* **Database Management System (DBMS):**
  Software for:
  * Defining
  * Storing
  * Querying
  * Updating
  * Administering databases

  *Shortly:* The tool we use to create databases.
* **Database System:** Application + Database + DBMS

#### DBMS Disadvantages

* It needs expertise.
* DBMS itself is expensive.
* The DBMS may be incompatible with any other available DBMS (interoperability).

---

### Database Users

* **Database Administrator (DBA):** Administer, maintain, tune, back up, manage permissions, and design at a physical level.
* **System Analyst:** Collects information from clients to write the RD (Requirement Document).
* **Database Designer:** Creates ERD and Database Mapping.
* **Database Developer:** Implements the database by creating tables, writing SQL queries, maintaining the database, and checking database performance.
* **Application Programmers:** Create the application or the web that has the database we're creating.
* **BI && Big Data Specialist (Data Scientist):** Analyze all the data to find patterns and support prediction/decision making. Discover the hidden relations between data.
* **End Users:** Anyone who interacts with the system to do their job.

---

### Entity Relationship Modeling

**ERD (Entity Relationship Diagram):** Identifies information required by the business by displaying the relevant entities and the relationships between them.

* **Entities:** Person, place, object, event, concept; has an independent existence and about which we store data.
* **Attributes:** Property or characteristic of an entity type.
* **Relationships:** Link between entities (using foreign keys).

#### ERD Shapes

* **Rectangles:** Entities
* **Diamonds:** Relationship sets (verbs)
* **Ellipses:** Attributes

*If there is an Attribute on a relationship, this means that this relationship has a property.*

#### Types of Entities

* **Strong Entity:** An entity that has a primary key.
* **Weak Entity:** An entity that does not have sufficient attributes to form a primary key; has a partial key.

#### Types of Attributes

* **Simple attribute:** If it cannot be subdivided into smaller parts.
* **Composite attribute:** If it can be divided into subparts.
* **Multi-valued attribute:** An attribute that can hold multiple values (*Double ellipse*).
* **Derived attribute:** If it can be calculated during runtime (*Dashed Ellipse*).
* **Complex Attribute:** Multi-valued + Composite.

#### Types of Relationships

* **Recursive Relationship (Unary):** A relationship in which the same entity participates more than once (degree 1).
* **Binary Relationship:** A binary relationship set is of degree 2.
* **Ternary Relationships:** A set of degree 3 (a relationship among 3 or more entities).

#### Types of Cardinalities (Mapping Cardinalities)

* **One-to-One:** Like 1 Person has one ID.
* **One-to-Many:** Like 1 department has many employees.
* **Many-to-Many:** Like many students take many courses.

#### Participation

* **Partial Participation:** Each entity of that type may or may not participate -> *represented by a single line*.
* **Total Participation:** Each entity of that type must participate -> *represented by 2 parallel lines*.

*Note: Any weak entity has to have a total participation.*

#### Types of Keys

* **Candidate Key:** A set of one or more attributes whose value can uniquely identify an entity in the entity set -> can be a primary key.
* **Primary Key:** A candidate key that is chosen by the database engineer as the unique identifier of an entity (Unique & Not NULL) -> *represented by a line under the attribute's value in the ERD*.
* **Foreign Key:** An attribute in one relation that references the primary key of another (or the same) relation.
* **Composite Key:** A primary key that is composed of two or more attributes together, not a standalone attribute.
* **Partial Key:** An attribute that uniquely identifies weak entities only within the context of their owner entity.
* **Alternate Key:** A candidate key that is not chosen as a primary key.
* **Super Key:** Any set of attributes that uniquely identifies a tuple (a candidate key is a minimal super key).
