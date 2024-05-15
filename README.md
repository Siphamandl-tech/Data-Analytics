# Data-Analytics
Notes for Data analytics converts raw data into actionable insights. It includes a range of tools, technologies, and processes used to find trends and solve problems by using data. Data analytics can shape business processes, improve decision-making, and foster business growth.

![image](https://github.com/Siphamandl-tech/Data-Analytics/assets/131585011/d8d2c0cc-b44f-423a-8710-d62c12657107)
Business landscape, data analytics is a compelling subject that transcends industry boundaries. Skills such as machine learning, data visualization, and narrative crafting are no longer exclusive to data scientists and analysts. They are becoming increasingly crucial for professionals across diverse sectors, educational backgrounds, and hierarchical levels.

Analytics programs allow businesses to access the untapped value locked within their data. Today, many organizations recognize the potential value of this work but are still in the early stages of developing their analytics programs.
Once data is in a suitable form, data professionals apply analytic techniques to draw conclusions from their data, create visualizations to depict the story of their data, and develop reports and dashboards to effectively communicate the results of their work to business leaders.

# Module 2: Data Preparation and Exploration
-Data Concepts and Environments
-Identify basic concepts of data schemas and dimensions
-Understanding the domain of Data Mining
-Explain data acquisition concepts
-Explain common techniques for data manipulation and query optimization

Exploring Databases
-Relational
-Nonrelational

Relational Databases(Structured data)
-
Relational databases are pieces of software that let you make an operational system out of an ERD. You start with a relational model and create a physical design. Relational entities correspond to database tables, and entity attributes correspond to table columns.

-Structure: Relational databases organize data into structured tables with rows and columns, where each row represents a record and each column represents a field or attribute.

-Query Language: SQL (Structured Query Language) is typically used to query and manipulate data in relational databases.

-Examples: MySQL, PostgreSQL, Oracle Database, Microsoft SQL Server.


Nonrelational Databases(Unstructured data)
-
A nonrelational database does not have a predefined structure based on tabular data. The result is a highly flexible approach to storing data. However, the data types available in relational databases are absent. As a result, you need to know more about the data itself to interact with it. Data validation happens in code, as opposed to being done in the database.

- Structure: Non-relational databases store data in various formats such as key-value pairs, documents, wide-column stores, or graph databases. They are designed to handle unstructured or semi-structured data.
  
- Query Language: NoSQL databases often have their own query languages or APIs tailored to the specific data model they use. Some support SQL-like querying, while others use JSON-like syntax or specialized APIs.
  
- Examples: MongoDB (document store), Cassandra (wide-column store), Redis (key-value store), Neo4j (graph database).

Data Structure:
If your data has a clear structure with well-defined relationships and a fixed schema, a relational database may be suitable. Non-relational databases are more flexible for handling diverse or evolving data structures.

Scalability:
Non-relational databases often offer better scalability options for distributed and big data applications.

Query Complexity:
Relational databases excel in complex queries involving joins, aggregations, and transactions, while NoSQL databases may be better suited for simpler, read-heavy operations.

Consistency vs. Flexibility:
Relational databases prioritize data consistency and ACID properties, whereas NoSQL databases may sacrifice strict consistency for greater flexibility and scalability.

# Database Use Cases
Databases tend to support two major categories of data processing: Online Transactional Processing (OLTP) and Online Analytical Processing (OLAP).

Online Transactional Processing
-
OLTP systems handle the transactions we encounter every day. Example transactions include booking a flight reservation, ordering something online, or executing a stock trade. While the number of transactions a system handles on a given day can be very high, individual transactions process small amounts of data. OLTP systems balance the ability to write and read data efficiently.

Online Analytical Processing
-
OLAP systems focus on the ability of organizations to analyze data. While OLAP and OLTP databases can both use relational database technology, their structures are fundamentally different. OLTP databases need to balance transactional read and write performance, resulting in a highly normalized design. Typically, OLTP databases are in 3NF.

Schema Concepts
-
The design of a database schema depends on the purpose it serves. Transactional systems require highly normalized databases, whereas a denormalized design is more appropriate for analytical systems. A data warehouse is a database that aggregates data from many transactional systems for analytical purposes. Transactional data may come from systems that power the human resources, sales, marketing, and product divisions. A data warehouse facilitates analytics across the entire company.

- A data mart is a subset of a data warehouse. 
- Data warehouses serve the entire organization, whereas data marts focus on the needs of a particular department within the organization.
- A data lake stores raw data in its native format instead of conforming to a relational database structure

- The star schema design to facilitate analytical processing gets its name from what the schema looks like when looking at its entity relationship diagram
- At the centre of the star is a fact table. Fact tables chiefly store numerical facts about a business.
- The schema design centres on reporting on the cost and profitability of procedures.
- Qualitative data, including names, addresses, and descriptions, is stored in a series of dimension tables that connect to the main fact table


When data moves from an OLTP design into a star schema, there is a significant amount of data duplication. As such, a star schema consumes more space than its associated OLTP design to store the same data. These additional resource needs are one of the factors that makes data warehouses expensive to operate.

![image](https://github.com/Siphamandl-tech/Data-Analytics/assets/131585011/2044a28a-0f6e-44ad-9d1a-d749408d2924)

https://d24jp206mxeyfm.cloudfront.net/assets/courseware/v1/c091c28615c1797c09308149855f56cf/asset-v1:CITI+DA+2023+type@asset+block/Figure_3-21_OLTP_and_OLAP_query_example.PNG


Dimensionality 
-
Dimensionality refers to the number of attributes a table has. The greater the number of attributes, the higher the dimensionality. A dimension table provides additional context around data in fact tables. For example, consider the Person_Dimension table in Figure 3.22, which contains details about people. If you need additional data about people, add columns to Person_Dimension.

Product dimension
Handling Dimensionality

-System functions are essential components of a computer system or software application that perform specific tasks or operations to manage, control, or support various functionalities.
-These system functions are fundamental to the operation of operating systems, software applications, and computer systems, enabling them to perform tasks efficiently, manage resources effectively, and provide a seamless user experience.

-Query optimization is a critical aspect of database management and performance tuning, aimed at improving the efficiency and speed of database queries. 
-By implementing these query optimization techniques and best practices, database administrators and developers can enhance the performance, scalability, and responsiveness of database systems, leading to improved user experience and operational efficiency.

















