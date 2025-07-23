### Power BI Project: Learning & Applying DAX Functions

 **Project Overview**:

   This project file,DAX.pbix, documents my hands on learning and practical application of DAX (Data Analysis Expressions) . The formula language used in Power BI for data modeling, aggregation, and analytical calculations. Throughout the training, I focused on creating calculated columns, measures, and applying context-aware logic to extract meaningful insights from data.

---

-  **What is DAX?**

    - DAX (Data Analysis Expressions) is a formula language used in Power BI, Excel Power Pivot, and SSAS Tabular models. It is designed for:

        - Creating custom calculations in calculated columns and measureS
        - Performing aggregations (SUM, AVERAGE, COUNT)
        - Enabling filtering, ranking, and logical comparisons
        - Working with time-based data using Time Intelligence

---

**Skills & Techniques Applied**

   - Below is a breakdown of the DAX techniques practiced, how they were implemented, and the purpose behind each one:

 1.  **Calculated Columns**

 - They are Columns created row-by-row during data load.
  
     -I Created full names from first and last name fields:
         -  DAX Function used: FullName = Customers[FirstName] & " " & Customers[LastName]
   
     -I Extracted year or month from a date column:
         - DAX Function Used: Year = YEAR(Sales[OrderDate])
    

     - **Purpose**: To enrich the data model with descriptive or derived fields that can be used in visualizations.

---

 2.  **Measures**
 - They are  Dynamic calculations that respond to filters and aggregations.
     
  - To  Calculate total sales:
    - DAX Function Used: Total Sales = SUM(Sales[Amount])
  
  - To Create average values:
    - DAX Function Used:Average Price = AVERAGE(Products[UnitPrice])
    
     - **Purpose**: Measures are optimized for performance and are the primary way to compute KPIs and other metrics in Power BI.

---

 3.  **Logical Functions**
   - They Perform conditional checks (like IF, SWITCH).

 - To Create product category tags based on price range:
   - DAX Function Used:Price Category = IF(Products[UnitPrice] > 100, "Premium", "Standard")

     - **Purpose**: Enables rule-based classification and dynamic labeling in reports.

---

 4.  **Time Intelligence**
 - Special DAX functions used to calculate over time (MTD, YTD, Previous Year, etc.)

  - To Create year-to-date sales:
    - DAX YTD Sales = TOTALYTD([Total Sales], Sales[OrderDate])
  
 - To Compare sales with previous period:
   - DAX Previous Year Sales = CALCULATE([Total Sales], SAMEPERIODLASTYEAR(Sales[OrderDate]))
    
      - **Purpose**: Time intelligence is key in tracking performance trends over periods.

---

 5.  **Filter and Row Context**
   - Filter Context: Refers to filters applied via slicers, visuals, or CALCULATE functions.
   - Row Context: Applies to calculated columns, where each row is evaluated individually.

     - Used CALCULATE() to modify the filter context in a measure:DAX Sales for Electronics = CALCULATE([Total Sales], Products[Category] = "Electronics")
  
   - **Purpose**: Mastery of context is essential to building accurate DAX logic.

---

 **File Details**
  - **Tool**: Power BI Desktop
  - **Main Focus**: DAX (Data Analysis Expressions)
  - **Areas Covered**:

     - Data modeling with DAX
     - Custom metrics using measures
     - Logic and classification with IF/SWITCH
     - Time-based comparisons using YTD and PY

---

 **Summary of What I Learned**:

   - The difference between calculated columns and measures
   - How to create custom KPIs and metrics
   - Applying logical conditions in business scenarios
   - Building time-intelligent dashboards
   - Understanding context behavior (row vs. filter)
