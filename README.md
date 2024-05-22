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


![image](https://github.com/Siphamandl-tech/Data-Analytics/assets/131585011/fac52b15-0c27-4a8b-bd96-ea36cafeb918)

Spreadsheets
-
The spreadsheet is the most widely used tool in the world of analytics. It is hard to imagine anyone who does not use spreadsheets as part of their work because they provide an intuitive way to organize our data into rows and columns. Spreadsheet software is installed on pretty much every computer in the modern work environment, and web-based spreadsheets are freely available to anyone.

Spreadsheets are productivity software packages that allow users to create documents that organize any type of data into rows and columns. Users may place any data they like in the spreadsheet and then quickly and easily perform mathematical calculations, such as finding the sum of the values in a row or searching out the minimum, maximum, mean, and median values in a dataset.

Spreadsheets lack any of the constraints of a relational database. While you can certainly organize data in a spreadsheet, there's no requirement that you do so. If you'd like, you can mix numbers, text, dates, and other data elements all in the same column. That does, of course, reduce the usefulness of the spreadsheet, but the user of spreadsheet software has total flexibility in how they organize their data.

Microsoft Excel is the most commonly used desktop spreadsheet application. It is available as a component of the widely deployed Microsoft Office productivity suite and most modern knowledge workers have access to it.
Excel then allows users to perform calculations and visualizations on their data. You may want to count the total number of restaurant inspections, determine the average length of time that an inspection takes, or compute the number of inspections conducted each day. You can perform almost any simple analysis you may need right in the Excel spreadsheet

Programming Languages
-
Programming languages allow skilled software developers to write their own instructions to the computer, allowing them to directly specify the actions that should take place during the analytics process.
Business analysts and data scientists need a way to be able to load, manipulate, and analyze data outside of the constraints of software written by another organization. In those cases, they might develop their own software to meet a specific need. In fact, many skilled analysts find it easier to write their own code to perform many analytics tasks than to work within another analytics package.

R
-
It is focused on creating analytics applications.
R also continues to grow in popularity because of its adoption by the creators of machine learning methods. Almost any new machine learning technique created today quickly becomes available to R users in a redistributable package, offered as open-source code on the Comprehensive R Archive Network (CRAN), a worldwide repository of popular R code.

One of the most important advances in the R language was the creation of a set of R packages known as the tidyverse by Hadley Wickham and other developers. The tidyverse approach to data analysis simplifies the use of the language and makes it accessible to anyone willing to invest a few hours in learning some basic syntax.

Most modern R developers choose to write, test, and deploy their code using an integrated development environment (IDE) called RStudio. This graphical interface, shown in Figure 3, provides a well-designed environment to manage your code, monitor its progress, and troubleshoot issues that might arise in your R scripts.
![image](https://github.com/Siphamandl-tech/Data-Analytics/assets/131585011/a6fd8b3b-4a94-428b-b8fa-7abeb828393e)

Python
-
Python is arguably the most popular programming language in use today. Python is about the same age as R, but the major difference between Python and R is that Python is a general-purpose programming language. This means that it is capable of creating software to meet just about any need you might imagine. You can do everything from code a video game to perform a complex data analysis in Python.
Python also has specialized libraries that focus on the needs of analysts and data scientists. In particular, the Python Data Analysis Library (pandas) provides a set of tools for structuring and analyzing data. Figure 4 shows an example of Python code performing data analysis.

![image](https://github.com/Siphamandl-tech/Data-Analytics/assets/131585011/50e6fc20-4286-4e75-945f-72c4fbb664e1)

Structured Query Language (SQL)
-
The Structured Query Language (SQL) is the language of databases. Any time a developer, administrator, or end user interacts with a database, that interaction happens through the use of a SQL command. SQL is divided into two major sublanguages:

The Data Definition Language (DDL) is used mainly by developers and administrators. It's used to define the structure of the database itself. It doesn't work with the data inside a database, but it sets the ground rules for the database to function.
The Data Manipulation Language (DML) is the subset of SQL commands that are used to work with the data inside of a database. They do not change the database structure, but they add, remove, and change the data inside a database.
As you prepare for the exam, you'll need to be familiar with the major commands used in SQL. It's important to understand that you are not responsible for writing or reading SQL commands. You just need to know what the major commands are and when you would use them.

There are three DDL commands that you should know:
-
-The CREATE command is used to create a new table within your database or a new database on your server.

-The ALTER command is used to change the structure of a table that you've already created. If you want to modify your database or table, the ALTER command lets you make those modifications.

-The DROP command deletes an entire table or database from your server. It's definitely a command that you'll want to use with caution!

There are also four DML commands that you should know:
-
-The SELECT command is used to retrieve information from a database. It is the most commonly used command in SQL as it is used to pose queries to the database and retrieve the data that you're interested in working with.

-The INSERT command is used to add new records to a database table. If you are adding a new employee, customer order, or marketing activity, the INSERT command allows you to add one or more rows to your database.

-The UPDATE command is used to modify rows in the database. If you need to change something that is already stored in your database, the UPDATE command will do that.

-The DELETE command is used to delete rows from a database table. Don't confuse this command with the DROP command. The DROP command deletes an entire database table, whereas the DELETE command just deletes certain rows from the table.

Users, administrators, and developers access databases in different ways.
-

First, a developer, administrator, or power user who knows SQL might directly access the database server and send it a SQL command for execution. This often happens through a graphical user interface, such as the Azure Data Studio interface shown in Figure 5. This tool allows you to write database queries in SQL, send them to the database, and then view the results.

Utilities like Azure Data Studio can do more than just retrieve data. They also offer a graphical way for database administrators to reconfigure a database. You can click through a series of menus to choose the changes you'd like to make to the database and the utility writes SQL commands that carry out your requests and sends them to the database.

![image](https://github.com/Siphamandl-tech/Data-Analytics/assets/131585011/2c1cf797-ed00-4eb0-83e4-089c47b58e19)

Statistics Packages
-
Of course, not everyone has the ability or desire to write their own software. It is often far simpler to work within software packages that provide the capabilities that we need. Statistics packages are a great example of this. These software packages go beyond the simple statistical analyses that are possible in spreadsheets and provide access to advanced statistical environments that are accessible through a graphical user interface and/or a built-in scripting language.

IBM SPSS
-
One of the most popular pieces of statistical software is IBM's SPSS package. SPSS is one of the oldest statistical software packages, first released in 1968, but it continues to be used today by many statisticians. Figure 6 shows an example of calculating the correlations between a set of variables using SPSS.
![image](https://github.com/Siphamandl-tech/Data-Analytics/assets/131585011/1fe43d80-1fd3-4b56-b459-592017facba9)

Stata
-
Stata is yet another statistical analysis package that dates back to the 1980s and continues to be updated today. It offers essentially the same features as SPSS and SAS and provides users with both a graphical interface and a command-line interface depending on their personal preference. Stata is less widely used than the more popular SAS and SPSS tools. Figure 8 shows an example of building and visualizing a linear regression model in Stata.
![image](https://github.com/Siphamandl-tech/Data-Analytics/assets/131585011/021a68d8-6a41-4a74-8817-4653c3faac9b)

Minitab
-
The final statistical software package covered on the Data+ exam is Minitab. And, once again, Minitab shares most of the same features as SPSS, SAS, and Stata but fits into the same category as Stata - an older tool that is not widely used today.
Moving on from statistics-focused tools, the industry also makes use of a set of graphical tools designed to help analysts build machine learning models without requiring them to actually write the code to do so. These machine-learning tools aim to make machine-learning techniques more accessible. Analysts may still tune the parameters of their models but do not necessarily need to write scripts to do so.

![image](https://github.com/Siphamandl-tech/Data-Analytics/assets/131585011/967cffc8-d32f-4e24-bc3a-d645accd22ec)


IBM SPSS Modeler
-
IBM's SPSS Modeler is one popular tool for building graphical machine learning models. Instead of requiring that users write code, it provides an intuitive interface where analysts can select the tasks that they would like the software to carry out and then connect them in a flowchart-style interface. Figure 10 shows an example of this interface being used to create a decision tree model of consumer credit data.

![image](https://github.com/Siphamandl-tech/Data-Analytics/assets/131585011/6c473af2-5a04-41ea-a361-0e88b01d22b4)


RapidMiner
-
RapidMiner is another graphical machine learning tool that works in a manner similar to IBM SPSS Modeler. It offers access to hundreds of different algorithms that may be placed in a visually designed machine-learning workflow. RapidMiner also offers prebuilt analytic templates for common business scenarios. Figure 12 shows the visual design of a decision tree task in RapidMiner.

Figure 11: Exploring a data model in SPSS Modeler
https://d24jp206mxeyfm.cloudfront.net/assets/courseware/v1/12084f9ec02261c73a262d6b57a92dc3/asset-v1:CITI+DA+2023+type@asset+block/Figure_11_Exploring_a_data_model_in_SPSS_Modeler.png

Figure 13 shows the result of creating this decision tree in RapidMiner. The presentation of results is not quite as visually appealing as the decision tree in SPSS Modeler, but it provides similar information to the analyst.
https://d24jp206mxeyfm.cloudfront.net/assets/courseware/v1/5e9c7712d34574cff2a662d4bf212140/asset-v1:CITI+DA+2023+type@asset+block/Figure_12_Designing_a_machine_learning_task_in_RapidMiner.png
![image](https://github.com/Siphamandl-tech/Data-Analytics/assets/131585011/2aae7c7b-c365-4918-af46-3e1fe856f123)
Figure 12: Designing a machine learning task in RapidMiner

![image](https://github.com/Siphamandl-tech/Data-Analytics/assets/131585011/e33af559-b253-472d-8780-ee1289035f94)
Figure 13: Exploring a data model in RapidMiner









