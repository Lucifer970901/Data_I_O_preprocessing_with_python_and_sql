# Data storage systems

Data storage: retaining digital information for later access.

### Data analytics lifecycle

this includes:
1. Define the problem
2. collect and preprocess the data
3. analyze data and identify insights
4. show results
5. Evaluate outcomes

data storage happens in step 2.

### Complexity of data storage

1. Text file: performs basic functions, retrive information later but   does not provide much structure
2. Structured file format like JSON: 
    step ip from flat files organize data heirarchically
3. Flat files like csv and xlsx:
    highly useful for structuring data in rows and columns
4. Relational database:
Store data in many tables each with rows and columns 

### How data storage needs to evlove

1. Scenario 1 tracking grocery list:
    size: just a few items  storage: phone's note app
2. Scenario 2: small delivery business:
    size: managing lists for multiple people, storage: spreadsheet program to efficient;ly track and share access.
3. large delivery business
    size: tens of thousands of customers data growing every week, in multiple regions with varying pricing tiers. seasonal coupons etc
    storage: will become increasingly slow, wiont update dynamically and easy to create conflicting versions or overwrite.

this is where database comes into picture

### Database

A structured system for storing data to handle huge volumes of data efficiently.

Think of database as: organized files +  specialized software

software handles:
* How data is added, removed or updated
* relationship between the files.

typically databases house on a server (or on a cloud) where many people can access them from their own computers
you can also store it on your own computer provided you have enough space


### Database advantages

* designed to handle large volume of data.
    * Efficient at storing and retrieving large volume of information. 
    * Use optimization techiniques to retrieve data quickly.
* Designed to handle concurrent users.
    * software handles conflicts and manages who interact with the information
* Database enforce constraints
    * example: certain value must be a number, all cells in row must be filled.
* Database model relationships
    * Connect related information across different tables
    * difficult to do in spreadsheets (using Xlookup)


### How to interact with database

* interact with database through querying
* database query can return: 
    * rows that meet certain conditions it can be summary statistics 
    * rows where multiple tables joined together.
    * Exactly the data you need
* you can query through:
    * website provided by the company or use code in python notebook.

### Type of databases

**Relational databases**

* organize data in well defined tables.
    records -> observations
    fields -> feature.
* each table represents an entity
* Each row represents one instance of entity.
* example: Customers that make orders   
    * Customer: Name, contact information
    * Product Name, order data
    * Connect to analyze how entities interact

**Non relational databases**

* Used to store data that varies in structure and content.
* Dont use tables with fixed columns
* Sacrifice strict consistency
* Provide better performance for high volume of data with flexible structure

### Database management systems (DBMS)

* Relational DBMS:
    * MYSQL
    * SQlite
    * Postgresql (postgres)
    * Oracle
    * presto -> netflix

* Non- relational DBMS
    * MongoDB
    * Cassandra

    