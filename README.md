# Tailwind-Traders-Sales
Tailwind Traders requires a detailed report that outlines the company’s latest sales data to shape its future sales strategies.

### Dashboard Link
https://app.powerbi.com/view?r=eyJrIjoiYzFhN2I1NzItZTUxZC00MGMzLThmNDEtOTU3MDAxOWExOTc4IiwidCI6IjIwMDFkMzc2LTA5ZGQtNDM5OC1hZjYwLTY1NzAyMzZhZjk3OSJ9

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
  1. Create a new column: yearly profit margin<br/>
    Yearly Profit Margin = 'Sales in USD'[Gross Revenue USD] / 'Sales in USD'[Net Revenue USD]
 
  2. Create a new measure for quarterly profit<br/>
    Quarterly Profit = 
    CALCULATE(
      'Sales in USD'[Yearly Profit],
      'CalendarTable'[Date]
    )
    * Leveraging the DATESQTD function in DAX to break down yearly data into quarterly segments.

  3. Create a new measure for the year-to-date profit<br/>
     Year-to-Date Profit = 
     TOTALYTD(
      'Sales in USD'[Yearly Profit],
      'CalendarTable'[Date]
     )
     * TOTALYTD is a function to aggregate data on a year-to-date basis

  4. create a new measure to represent the median sales
     
- Access the Performance Analyzer
  Recording the performance of the card visuals, observing their respective load times, and ensuring the DAX query time of visual items is < 200ms

  
### Create an executive dashboard
- Publish 'Sales Overview' and 'Profit Overview' dashboards, and create an executive dashboard in Power BI service to curate data efficiently.
- Display sales summaries focusing on product quantities and median sales trends.
- Highlight profit metrics, emphasizing net revenue and Yearly Profit Margin by country.
- Use card visualizations for quick insights.
- Ensure the dashboard is mobile-friendly, making important data accessible.


### Configure alerts and subscriptions
- Create a daily alert for Gross Revenue USD
- Create a subscription for the Sales Overview and Profit Overview tab

  
### Data Visualization and Storytelling
1. Loyalty Points Insights: Key Markets Identified
The data reveals that the **UK** and the **USA** lead in total loyalty points, highlighting them as Tailwind Traders’ most engaged and potentially loyal customer bases. This suggests an opportunity to strengthen these markets further by introducing exclusive loyalty programs or tailored promotions that reward high point accumulation.

2. Product Popularity: Best-Selling Items
Three products dominate customer preference:
* Floral Wallpaper
* Porcelain Dinner Set
* ProCarpenter Toolkit<br/>
These items’ popularity underscores their appeal across diverse customer segments. Investing in inventory expansion or offering bundled deals for these products could drive even higher sales.

3. Consistent Performance Across Countries: Sales and Profit
Median sales figures show a balanced distribution across all countries, with **France** standing out for the highest median sales and profit margins. This even distribution suggests Tailwind Traders has successfully penetrated multiple markets, but France’s outperformance signals a prime location for further investment, such as regional marketing campaigns or partnerships.

4. Revenue Champion: Modular Sofa Set
The Modular Sofa Set emerges as the product with the **highest net revenue**, indicating strong profitability despite its potentially higher price point. Tailwind Traders could consider promoting this product as a flagship offering, highlighting its value through targeted advertising or premium customer experiences.

5. Profit Margins: A Volatile October
October 2023 saw the most significant fluctuations in **yearly profit margin**, suggesting operational or market challenges during this period. Analyzing the specific factors—such as supply chain disruptions, seasonal demand changes, or unexpected costs—could provide insights to stabilize margins in the future.



### Actionable Insights for Future Sales Strategies
- **Leverage Loyalty Programs in Key Markets**: Focus on the UK and USA with personalized offers to capitalize on high loyalty points.
- **Boost Sales of Popular Products**: Offer bundles or discounts on Floral Wallpaper, Porcelain Dinner Sets, and ProCarpenter Toolkits.
- **Strengthen High-Performing Regions**: Increase marketing efforts and partnerships in France to maximize its potential.
- **Promote High-Revenue Products**: Position the Modular Sofa Set as a premium offering to maximize revenue.
- **Mitigate Profit Volatility**: Investigate October’s fluctuations and implement risk management strategies to ensure steady profit margins.



