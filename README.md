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


Working with Data
-
- To turn a database design into an operational database ready to accept data, you use the *Data Definition Language (DDL)* components of SQL. DDL lets you create, modify, and delete tables and other associated database objects.

- To generate insights, a productive analyst must be comfortable using the Data Manipulation Language (DML) capabilities of SQL to insert, modify, and retrieve information from databases. While DDL manages the structure of a database, DML manages the data in the database.

Filtering and Logical Operators
-
A query can have multiple filtering conditions. You need to use a logical operator to account for complex filtering needs. For example, suppose you need to retrieve the name and breed for dogs weighing more than 60 pounds. In that case, you can enhance the query using the AND logical operator, as follows:

SELECT Animal_Name, Breed_Name

FROM  Animal

WHERE Animal_Type = 'Dog'

AND  Weight> 60

The AND operator evaluates the Animal_Type and Weight filters together, only returning records that match both criteria. OR is another frequently used logical operator. For example, suppose you want to see the name and breed for all dogs and any animals that weigh more than 10 pounds regardless of the animal type. The following query delivers the answer to that question:

SELECT Animal_Name, Breed_Name

FROM  Animal

WHERE Animal_Type = 'Dog'

OR   Weight> 10

Complex queries frequently use multiple logical operators at the same time. It is good to use parentheses around filter conditions to help make queries easy for people to read and understand.

Sorting
-
When querying a database, you frequently specify the order in which you want your results to return. The ORDER BY clause is the component of a SQL query that makes sorting possible. Similar to how the WHERE clause performs, you do not have to specify the columns you are using to sort the data in the SELECT clause.

For example, suppose you want to retrieve the animal and breed for dogs over 60 pounds, with the oldest dog listed first. The following query delivers the answer:

SELECT  Animal_Name, Breed_Name

FROM   Animal

WHERE  Animal_Type = 'Dog'

AND   Weight> 60

ORDER BY Date_of_Birth ASC

IFF(boolean_expression, true_value, false_value)
-
As you can see from the syntax, the IFF function expects the following three parameters:

Boolean Expression:  The expression must return either TRUE or FALSE.
True Value:  If the Boolean expression returns TRUE, the IFF function will return this value.
False Value:  If the Boolean expression returns FALSE, the IFF function will return this value.
The following query, using the IFF function, generates the results in Table 3.11:

SELECT  Animal_Name, IFF(Sex = 'M', 'Male', 'Female')

FROM   Animal

Query Optimization
-
Writing an SQL query is straightforward. Writing a SQL query that efficiently does what you intend can be more difficult. There are several factors to consider when creating well-performing SQL.
- Parametrization

- Indexing
  
- Data subsets and Temporary Tables
  
- Execution Plan

Chapter Summary
-

![image](https://github.com/Siphamandl-tech/Data-Analytics/assets/131585011/27b132ba-92dc-44ef-a721-382dc0e3b71f)

Databases are technology platforms for processing and storing data. There are two primary types of databases: relational and non-relational. Relational databases are ideal when you have tabular data, while there are numerous non-relational offerings when you need more flexibility than the structure a relational database imposes.

Using a relational database as a technology platform, you can build transactional or analytical databases to address the business need. Transactional (OLTP) and analytical (OLAP) databases require different schema design approaches. Since a transactional database needs to balance reading and writing data, it follows a highly normalized schema design.

On the other hand, analytical databases prioritize reading data and follow a denormalized approach. The star and snowflake schema designs are two approaches to structuring data for analysis. Both methods implement dimensional modeling, which organizes quantitative data into facts and qualitative data into dimensions.

There are multiple ways to acquire data for analysis. For example, most data warehouses source data from transactional systems. To copy data from a transactional system, you can use an ETL or ELT approach. ETL leverages technology external to a relational database to transform data, while ELT uses the power of a relational database to do the transformation. Depending on the rate of change and data volume, you can take a complete refresh or delta load approach.

You can also acquire data from external sources. APIs are integration components that encapsulate business logic and programmatically expose data. It is common to interact with APIs to source data for both transactional and analytical purposes. You may also find yourself needing to scrape data from a website or pull data from a public database.

There are times when you need primary source data that you cannot obtain programmatically. In that case, you may end up conducting a survey or observing people and processes.

Once you have data in a relational database, you need to be comfortable manipulating it. Structured Query Language (SQL) is the standard for relational data manipulation. With SQL queries, you can filter, sort, compare, and aggregate data.

There are times when you will be working with large volumes of data that impact performance. There are several approaches you can take to mitigate performance issues. When writing frequently executed queries, make sure you use parametrization to reduce the database's parsing load. Reducing the number of records you're working with is another viable approach, which you can achieve by subsetting the data and using temporary tables. If you have queries taking more time than you expect, work with a database administrator to review the query's execution plan and ensure you have the appropriate indexing strategy.


![image](https://github.com/Siphamandl-tech/Data-Analytics/assets/131585011/896b1899-82da-4424-8f22-65775d2e5fb8)

A good analyst needs a firm understanding of why data needs to be clean, techniques for cleaning, and ways to verify data quality.

When assessing data quality, keep in mind that organizations with complex systems frequently encounter data duplication challenges. When an organization integrates multiple systems, you need to be on the lookout for redundant data. Apart from duplication and redundancy, you need to check data values for inconsistencies. Inconsistencies can include data that is missing, that falls outside an expected range of values, or that does not match the target data type. Keep in mind that outliers have an outsized effect on statistical analysis. When initially exploring your data, it is imperative to identify, understand, and address any outliers in your data.

When preparing data for analysis, there are numerous manipulation techniques you can use. Analysts need a deep understanding of how your data sources will work together. You may have to merge or blend sources or concatenate or split columns within an individual source. Depending on your statistical technique of choice, you may end up recoding a categorical variable as numeric. In today's world, there is an overabundance of data. You may need to reduce the number of rows or columns to facilitate your analysis.

Invariably, you will want to compare the effects of different attributes. Recall that when you have multiple columns using disparate measurements, you need to normalize the data values. Normalizing avoids exaggerating the impact of a column based on the numeric values it contains.

Recognizing opportunities where data quality errors can occur is essential for the modern data analyst. Data acquisition, transformation, conversion, manipulation, and visualization are steps in the analytical process where quality issues arise. Beyond recognizing when quality errors happen, an analyst needs to consider automatically injecting quality improvements into data collection and preparation processes.

When thinking about how to assess quality, keep in mind the dimensions of data quality. It is essential to define your business objectives through the lenses of data accuracy, completeness, consistency, uniqueness, and validity. Having the right data at the right time improves your ability to make data-informed decisions.

Once you understand where your data comes from and how you are going to use it, be sure to define ways in which you will continuously assess its quality. Quality assessment methods include everything from reasonable expectations and audits to advanced statistical techniques.


![image](https://github.com/Siphamandl-tech/Data-Analytics/assets/131585011/bee4bffd-93b9-4665-8feb-48b5de989368)

Wielding statistical techniques to analyze data is a cornerstone ability of the modern data analyst. It is imperative to appreciate the difference between census and sample data. A census consists of an observation of every member of the population, whereas a sample is data about a specific subset. Since it is frequently prohibitive to obtain a census, analysts typically work with sample data. Whether you are working with census or sample data, you end up using statistics.

Descriptive statistics is a branch of statistics that describes a dataset. Descriptive statistics help you understand the data's characteristics and can help understand events that have already happened. One category of descriptive statistics is measures of frequency. Measures of frequency shed light on recurring values in your data. Count is the most common measure of frequency. For example, one of the first things an analyst does when encountering a new table in a database is to get the total number of rows by issuing the following SQL statement:

SELECT COUNT(*) FROM <table_name>

Once you understand the total number of rows you are dealing with, it is common to understand proportions in the data to check for bias. For example, if the population you are studying is split evenly between men and women, you would expect that any random sample from the population would have an equal proportion of men and women.

Measures of central tendency are descriptive statistics that help you understand how tightly or widely distributed your data is. Mean, median, and mode are all measures of central tendency. Exploring how far apart the mean and median values are can tell you whether you are working with data that follows a normal distribution. If the mean and median are close, the distribution is likely normal. If the mean and median are far apart, the data is skewed to one side.

Measures of dispersion help you understand how widely distributed your data is. The range, or difference between maximum and minimum values, establishes the upper and lower limits for numeric variables in your data. Variance is a dispersion measure that calculates how far each observation in a dataset is from its mean value and is most often used as a path to calculating standard deviation. Standard deviation, or the square root of variance, is a frequently referenced statistic due to the empirical rule, stating that almost every observation falls within three standard deviations from the mean in a normal distribution.

Measures of position help identify where a specific value for an observation is relative to other values. The interquartile range is a valuable measure of position, as it places all values of a variable into one of four quartiles where 50 percent of the values in a dataset are in the second and third quartiles.

Inferential statistics differs from descriptive statistics in that you can use inferential statistics from a sample to draw conclusions about the population. Making generalizations about the population using sample data is a powerful concept that enables impactful decisions.

When performing statistical inference, you have a degree of uncertainty as inferential statistics are based on probabilities. Confidence intervals help you understand how a test statistic relates to its corresponding population parameter. A confidence interval provides the upper and lower limits for a given confidence level that the population parameter falls within the confidence interval's range. The higher the confidence level, the wider the range of values that fall within the confidence interval.

You also use statistics to conduct hypothesis tests. Hypothesis tests assert two mutually exclusive statements in the form of the null and alternative hypotheses. When hypothesis testing, you seek to reject the status quo of the null hypothesis by using statistics to assert that the alternative hypothesis is plausible.

The sample size impacts the distribution you use when conducting hypothesis tests. When working with numeric data, you can use the normal distribution if you know the population standard deviation and have a sample size greater than 30. However, if the population standard deviation is unknown or the sample size is less than 30, you use the t-distribution. If you are working with categorical data, you use the chi-square distribution for comparison purposes.

You have to account for potential mistakes when hypothesis testing. A Type I error is a false positive when you reject the status quo when it is true. A Type II error is a false negative when you accept the status quo when it is false.

Regardless of the statistics you use, it is crucial to have a systematic approach when conducting an analysis. Having a clearly defined scope that the business representative agrees on is imperative. You also need to have access to good sources of data. With these two things in place, you initiate an analytics project by performing an exploratory data analysis (EDA). The EDA will inform you about the type of data you are working with and whether you have any missing data or outlier values, and it will provide summary statistics about each variable in your dataset.


Differentiate between descriptive and inferential statistics. 

Descriptive statistics help you understand past events by summarizing data and include measures of frequency and measures of dispersion. Inferential statistics use the powerful concept of concluding an overall population using a sample from that population.

Calculate measures of central tendency. 

Given a dataset, you should feel comfortable calculating the mean, median, and mode. Recall that the mean is the mathematical average. The median is the value that separates the lower and higher portions of an ordered set of numbers. The mode is the value that occurs most frequently. While mean and median are applicable for numeric data, evaluating the mode is particularly useful when describing categorical data.

Explain how to interpret a p-value when hypothesis testing. 

Recall that p-values denote the probability that a test statistic is as extreme as the actual result, presuming the null hypothesis is true. The lower the p-value, the more evidence there is to reject the null hypothesis. Generally speaking, it is safe to consider p-values under 0.05 as being statistically significant. With p-values greater than 0.05, there is less evidence supporting the alternative hypothesis.

Explain the difference between a Type I and Type II error. 

When hypothesis testing, a Type I error is a false positive, while a Type II error is a false negative. Suppose you have a null hypothesis stating that a new vaccine is ineffective and an alternative hypothesis stating that the vaccine has its intended impact. Concluding that the vaccine is effective when it isn't is a Type I error. A Type II error is a false conclusion that the vaccine does not work when it does have the intended effect.

Describe the purpose of exploratory data analysis (EDA). 

One of the first things you should perform with any new dataset is EDA, a structured approach using descriptive statistics to summarize the characteristics of a dataset, identify any outliers, and help you develop your plan for further analysis.
















