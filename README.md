# Tailwind-Traders-Sales

### Data Cleaning in Excel
Create new variables: Gross Revenue, Total tax, and Net Revenue (actual earnings post-tax for each product)

### Data Transformation in PowerBI
- Load Sales dataset
- Change data types
- Check Column Quality, Column Distribution, and Column Profile
- Load Purchases dataset, and repeat the same procedure as above
- Filter the ReturnStatus column to ensure that only records with Not Returned are visible
- Load Countries dataset, and repeat the same procedure as above
- Load the Historical currency exchange data with Python script

### Data Modelling
- Create relationships between tables
- Create new tables: Calendar table, Sales in USD calculated table, and manage their relationships with other tables
- Create new measures using
  ### DAX Calculation
  1. Create a new column: yearly profit margin
    Yearly Profit Margin = 
    DIVIDE(
      SUM('Sales in USD'[Gross Revenue]),
      SUM('Sales in USD'[Net Revenue]),
      0
    )
 
  2. Create a new measure for quarterly profit
    Quarterly Profit = 
    CALCULATE(
      'Sales in USD'[Yearly Profit],
      'CalendarTable'[Date]
    )
    Leveraging the DATESQTD function in DAX to break down yearly data into quarterly segments.

  3. Create a new measure for the year-to-date profit
     Year-to-Date Profit = 
     TOTALYTD(
      'Sales in USD'[Yearly Profit],
      'CalendarTable'[Date]
     )
     TOTALYTD is a function to aggregate data on a year-to-date basis

  4. create a new measure to represent the median sales
     
- Access the Performance Analyzer
  Recording the performance of the card visuals, observing their respective load times, and ensuring the DAX query time of visual items is < 200ms

  

