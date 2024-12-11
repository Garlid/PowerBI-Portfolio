#Microsoft Power BI Desktop for Business Intelligence
I completed Maven Analytic's course Microsoft Power BI Desktop for Business Intelligence course <https://www.udemy.com/course/microsoft-power-bi-up-running-with-power-bi-desktop/?couponCode=KEEPLEARNING> in December 2024. The following are key takeaways that enhanced my current understanding of Power BI Desktop.

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
- one important thing about connecting multiple fact tables is that they should connec through shared dimension talbes and not directly to each other
- filter flow is also important when it comes to later aspects of building out reports. filter direction is important because the filter context is passed to downstream tables, following the arrow's direction. this is one thing that was confusing to me when i first started with power bi
- one pro tip maven analytics gave was to design the models with one-way filters and 1 to many cardinality whenever possible


###Calculated fields with DAX
- one thing that i definitly did wrong when i started with power bi was using calculated columns for creating numerical values. i learned that calucalted columns are better for filtering and grouping the data. so a great way to use calculated columns is for feature engineering. one feature we engineered was a Parent column. If there was a number greater than 0 in the children column we added a cacluated column that indicated a "yes" for parent. otherwise, the parent value was "no".
- I also learned the importance of having a measures table. the project in this repository utilizes a measures table for aggregate values
- i also learned that implicit measures are a raw numerical field from a table that is used in a visual with an aggregation function, while explicit measures are those i create using DAX
- calculated columns do not use filter context, while measures are evaluated based on filter context, so they recalculate whenever the fields/filters around them change
- i was already fairly familiar with DAX, but this course provided a good refresher as well as introduced me to a few new functions, specifically date/time functions
- one thing i was confused about before was why measure totals didnt add up. i learned that measures may seem incorrect because they don't simply add up the visible values in the report
- The CALCULATE function evaluates an expression in a context that is modified by filters (like visual filters)
- The ALL function returns all rows in a table, or all values in a column. it ignores any filters that have been applied. This is great for the percent of total calculations when teh denominator needs to be fixed regardless of filter context
- The FILTER function returns a table that is a subset of another table or expression. it is often nexted with calculate or SUMX. BUT, I learned that FILTER can be slow, so only use filter if a simple caluclate function doesn't work
- one thing that was confusing when i first started with DAX was why there were functions like "sumx". why not just use sum? well that's because the X indicates an iterator function to loop through the same expression on each orw of a table, and then applies aggregation to the results. one example we did in our project was adding a total cost measure. to do this we used the following DAX:
  total cost = 
SUMX(
  'Sales Data',
'Sales Data'[order quantity]
*
Related(
'Product Lookup'[Product Cost]
)
)
So what this dax did in our project was to first loop through each row of the Sales Data table and multiple the order quantity by the product cost column in the product lookup table. then it summed it up. but it did it in a way that we didn't need to add redundant columns to our Sales table. 

- Other Dax functions we went over were time intelligence functions, like DateAdd,DatesYTD, and DasteInPeriod. This was used measures like Previous Month Orders, Previous Month Profit etc, which can be seen in the Adventure Works Final Report in this repository


###Visualizing Data
- After the foundationals, we dove into building a dynamic, interactive report
- I was very excited to dive into this section
- the three key questions i never asked myself before this course are:
1. What type of data am i working with?
2. what do i want to communicate?
3. Who is the end user and what do they need?
- things i hadn't considered for what i want to communicate were types of visuals. do i want to compare the datea? show the break down or composition of the data? show the distrubiton of the data? or show the correlation or relationship between the data?
- Then there werew a few steps for designing dashboards:
1. define the purpose
2. choose the right metrics
3. present the data effectively
4. eliminat clutter and nose
5. use layout to focus attention
6. tell a clear story
- so for the project in this repo there are a few different pages that are currated for different audiences (execs, managers, and analysts)
