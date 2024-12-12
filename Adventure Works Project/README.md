# Microsoft Power BI Desktop for Business Intelligence

I completed Maven Analytics' course, **[Microsoft Power BI Desktop for Business Intelligence](https://www.udemy.com/course/microsoft-power-bi-up-running-with-power-bi-desktop/?couponCode=KEEPLEARNING)**, in December 2024. This course enhanced my understanding of Power BI Desktop and provided valuable insights into various aspects of data analysis and visualization.

## Key Takeaways

### Connecting & Shaping Data

- Managing data connections efficiently.
- Utilizing table transformation tools (e.g., renaming columns, assigning data types, removing columns, extracting specific data, and creating new columns).
- Performing web scraping using the native Web Connector.
- Leveraging data profiling tools (e.g., column distribution) to begin Exploratory Data Analysis (EDA).
- Applying text and numeric tools to prepare data for analysis.
- Understanding the importance of a calendar table and learning to create rolling calendar tables.
- Recognizing that table transformations and column calculations should be as close to the original data source as possible for optimized performance.
- Shaping data using append and merge queries.
- Pivoting and unpivoting columns effectively.
- Establishing organized table names and a structured file system to improve project workflow.

### Creating a Data Model

- Gained a deeper understanding of database normalization: "The process of organizing tables and columns in a relational database to reduce redundancy and preserve data integrity." (Maven Analytics)
  - Benefits include decreased table sizes, simplified queries, and reduced errors.
  - Learned the distinct purposes of fact and dimension tables:
    - **Fact tables**: Quantitative data, typically containing numerical values.
    - **Dimension tables**: Descriptive data, such as dates or product details.
- Strengthened my knowledge of primary and foreign keys:
  - **Primary Keys**: Unique identifiers for each row in a table.
  - **Foreign Keys**: Reference primary keys from other tables and may appear multiple times within the same table.
- Improved data modeling skills:
  - Avoiding "flat file" designs by connecting multiple tables through shared dimension tables rather than directly linking fact tables.
  - Understanding relationship cardinality (e.g., one-to-many relationships).
  - Designing models with one-way filters and maintaining optimal cardinality wherever possible.
- Explored common data model schemas:
  - **Star schema**: A central fact table surrounded by dimension tables.
  - **Snowflake schema**: A more complex structure with sub-dimension tables.
- Learned about filter direction and context in relation to report-building.

### Calculated Fields with DAX

- Differentiated between calculated columns and measures:
  - Calculated columns: Ideal for filtering and grouping data (e.g., creating a "Parent" column based on values in a "Children" column).
  - Measures: Used for aggregation and recalculation based on filter context.
- Established a **measures table** for better organization and performance.
- Explored DAX functions:
  - **CALCULATE**: Modifies filter context for an expression.
  - **ALL**: Ignores filters for calculations.
  - **FILTER**: Subsets a table or expression; useful but can impact performance.
  - Iterator functions (e.g., **SUMX**): Loop through rows and apply aggregation to the results.
- Practical example:
  ```DAX
  Total Cost = SUMX('Sales Data', 'Sales Data'[Order Quantity] * RELATED('Product Lookup'[Product Cost]))
  ```
- Explored time intelligence functions (e.g., **DateAdd**, **DatesYTD**, **DatesInPeriod**) for trend analysis and period comparisons.

### Visualizing Data

- Developed skills to create dynamic, interactive reports.
- Key considerations for effective visualization:
  - Understand the type of data being used.
  - Define the communication goals.
  - Identify the end user's needs.
- Dashboard design principles:
  - Define the purpose.
  - Choose appropriate metrics.
  - Present data effectively.
  - Eliminate clutter and noise.
  - Use layout to focus attention.
  - Tell a clear story.
- Designed report pages for various audiences (executives, managers, analysts), including:
  - Executive summary
  - Product details page
  - Geospatial view (map)
  - Customer details

The final project utilizes a snowflake schema and includes examples of DAX calculations and visualizations. The report is available [here](https://github.com/Garlid/PowerBI-Portfolio/blob/main/Adventure%20Works%20Project/Adventure_Works_Report_Final.pdf).

