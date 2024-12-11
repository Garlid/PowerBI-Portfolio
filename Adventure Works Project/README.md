#Microsoft Power BI Desktop for Business Intelligence
I completed Udemy's Microsoft Power BI Desktop for Business Intelligence course <https://www.udemy.com/course/microsoft-power-bi-up-running-with-power-bi-desktop/?couponCode=KEEPLEARNING> in December 2024. The following are key takeaways that enhanced my current understanding of Power BI Desktop.

##Key Takeaways
###Connecting & Shaping Data
- Managing data connections
- Better utilizing table transformation tools (renaming columns, assigning data types to columns, removing columns, extracting specific data from a column and creating a new column with the extracted data)
- Internet scraping  via the native Web Connector
- Utilizing data profiling tools (ie, column distribution) to being EDA on the data sets
- Better using text tools and numeric tools to format the data and prepare it for further use
- Understanding the importance of having a calendar table
- Creating rolling calendar tables
- I learned that, as a best practice, table transformations and column calculations should happen as close to the original data source as possible. This optimizes speed and performance for the report.
- shaping data through append and merge queries
- Pivoting and unpivoting columns 
- One thing I didn't understand when I started using Power BI was that I should define my table names and have an organized file structure to begin with

###Creating A Data Model
- When i started this course, I didn't understand how to properly establish a data model
- I learned what database normalization is - "the process of organizing the tables and columns in a relational database to reduce redundancy and prserve data integrity" - maven analytics
- Database normalization helps to decrease table sizes, simplify queries, and reduce errors
- Each table in a normlized database should have a distinct and specific purpose
- I also learned what fact and dimension tables are
- Fact tables are usually tables that contain numeric values, while dimension tables have more descriptive data (including dates)
- Fact tables are quantitative in nature (the word "fact" table reminds me of "math facts" from elementary school, and those are numerical of course)
- Dimensions describe something or someone, so like a product has different "dimensions" to it
- i was familiar with the idea of primary and foreign keys, but this gave me a better understanding of it
- Primary Keys uniquely identify each row of a table. there is only one primary key for each row
- a foreign key relates to the primary key of another table. a foreign key can be listed for multiple rows of the same table
- one thing the instructor pointed out was that we should NOT pull everything into a single table. that was definitly something i attempted when i was new to power bi. but this course taught me how to structure my data model in a way so i didn't have to do that
- i also learned about two common data model schemas - namely, the star schema and the snowflake schema
- a star schema is a very simple data model, where there is a single fact table surrounded by dimension tables
- a snowflake schema is similar to a star schema, but it is slightly more complicated in the sense tha tit contains sub-dimension tables as well
- the finished project you see in this repository utilizes a snowflake schema
- i learned about relationship cardinality and the purposes of it
- cardinality "refers to the uniqueness of values in a column". the instructor said to ideally use the one-to-many cardinalyt. one instance of each primary key and many instance of each foreign key
