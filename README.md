# Customer Service Ticket Analysis

## Project Overview
This Excel-based analysis project provides comprehensive insights into customer service ticket data, helping identify trends, measure performance metrics, and support data-driven decisions for customer service improvement.

## Project Structure

### 1. Data Preparation and Cleaning
- Data imported from customer service ticketing system
- Formatted as an Excel table for easier analysis
- Missing values identified and handled
- Date fields converted to proper Excel date format
- Text fields standardized using PROPER() and TRIM() functions

### 2. Key Performance Metrics Summary
- Created "Summary" sheet with essential metrics:
  - Total ticket count: `=COUNTA(Data!A:A)-1`
  - Average first response time: `=AVERAGEIF(Data!N:N,"<>0",Data!N:N)`
  - Average resolution time: `=AVERAGEIF(Data!O:O,"<>0",Data!O:O)`
  - Average satisfaction rating: `=AVERAGE(Data!P:P)`
  - Resolution rate: `=COUNTIFS(Data!K:K,"Resolved")/COUNTA(Data!A:A)-1`
  - SLA compliance: `=COUNTIFS(Data!N:N,"<24")/COUNTA(Data!N:N)`

### 3. Ticket Status Analysis
- Created PivotTable showing count of tickets by status
- Calculated resolution rate as percentage of total tickets
- Generated bar chart visualization of ticket volume by status

### 4. Ticket Priority Analysis
- Created PivotTable showing count of tickets by priority level
- Formatted results as percentage of total tickets
- Calculated average resolution time per priority level
- Created column chart of response time by priority

### 5. Support Channel Analysis
- Created PivotTable analyzing tickets by channel (email, phone, chat, etc.)
- Compared metrics across channels: ticket volume, response time, resolution time
- Generated pie chart showing ticket distribution by channel

### 6. Time-Based Analysis
- Created helper columns extracting date components:
  - Month: `=MONTH(DateOfPurchase)`
  - Day: `=DAY(DateOfPurchase)`
  - Weekday: `=WEEKDAY(DateOfPurchase,1)`
- Created PivotTable showing trends over time
- Generated line chart displaying ticket volume trends

### 7. Customer Demographics Analysis
- Created age group categories using nested IF function:
  - `=IF(CustomerAge<25,"Under 25",IF(CustomerAge<40,"25-39",IF(CustomerAge<55,"40-54","55+")))`
- Created PivotTable with gender in rows and age groups in columns
- Analyzed satisfaction ratings across demographic segments

### 8. Product-Related Analysis
- Created PivotTable with products in rows and ticket types in columns
- Analyzed which products generate most tickets
- Calculated average resolution time by product
- Identified products with highest/lowest satisfaction ratings

### 9. Correlation Analysis
- Analyzed relationship between first response time and satisfaction:
  - `=CORREL(FirstResponseTime,CustomerSatisfactionRating)`
- Analyzed relationship between resolution time and satisfaction:
  - `=CORREL(TimeToResolution,CustomerSatisfactionRating)`
- Created scatter plots to visualize these relationships

### 10. Data Visualization
- Created standardized charts for key metrics:
  - Bar chart: Ticket volume by status
  - Pie chart: Ticket distribution by channel
  - Column chart: Response time by priority
  - Heat map: Satisfaction ratings by product (using conditional formatting)
  - Line chart: Ticket volume over time

### 11. Key Performance Indicators
- Calculated critical performance indicators:
  - First response time SLA compliance percentage
  - Resolution time SLA compliance percentage
  - Percentage of tickets with high satisfaction ratings (4-5)

### 12. Interactive Dashboard
- Created consolidated "Dashboard" sheet
- Referenced key metrics using GETPIVOTDATA() function:
  - `=GETPIVOTDATA("Count of Ticket ID",'Status Analysis'!$A$3,"Ticket Status","Resolved")`
- Added critical charts and visualizations
- Implemented interactive slicers for filtering:
  - Product filter
  - Channel filter
  - Priority filter

## Technologies Used
- Microsoft Excel
- Excel PivotTables and PivotCharts
- Excel Formulas (COUNTIFS, AVERAGEIF, CORREL, IF, etc.)
- Conditional Formatting
- Excel Slicers for interactive filtering

## How to Use This Analysis
1. Navigate between sheets using the tabs at the bottom
2. Review the "Summary" sheet for quick insights
3. Explore individual analysis sheets for deeper understanding
4. Use the "Dashboard" sheet for interactive exploration
5. Use slicers to filter data by product, channel, or priority
6. Refresh PivotTables if new data is added (right-click > Refresh)

## Future Enhancements
- Implement Power Query for more advanced data transformation
- Add trend forecasting using trendline analysis
- Create additional drill-down capabilities
- Set up automated reporting using Power Automate

## Project Status
Completed as Project #2 at Future Intern

## Author
FRIDA KATANA KITSAO 
Future Intern  
https://www.linkedin.com/in/frida-katana-kitsao-701433231/

## Acknowledgments
Special thanks to the Future Intern program for providing the opportunity to work on this meaningful project focused on improving customer support through data analysis.
