
# Sales Team Performance Report using Power BI

### Domain: Fast Moving Consumer Goods

#### Problem Statement: 
Candy Land is a manufacturer of candies having  
4 products, Delish, Jucies, Tempo and Yummies. 

They have 25 salespersons who sell the products to the retail store starting from the small mom & pop store to the big retail giants. 

In this report we are analysing sales KPIs of each product and product level performance of each of the sales persons. 

The KPIs we are considering here are, 
- Target Sales
- Actual Sales 
- Variance from the Target Sales

#
### Data Source:
Excel Sheet
#
### Steps Followed: 
Step 1: Importing the data provided on the excel sheet. 

Step 2: Loading the data into Power Query for transforming it into usable format.

The tables we have received have the following data, 
- Actual Sales 
- Target Sales 
- Sales People Detail

The data we have received is in a pivot table format. Which is not usable for the intended report. 

Step 3: Promoted the column headers. 

Step 4: Unpivoted the columns of the Actual Sales and Target Sales tables to get 3 columns, 
- Sales Person 
- Month of Sale
- Amount od Sale

Step 5: Creating a date table that can be mapped to the date fields of the fact table in a later stage.

Step 6: Creating relationships between the tables under Model View tab using the Manage Relationship option.

![Image](https://github.com/user-attachments/assets/b1a92993-a1fa-42d2-be2f-87b0548ad8f7)

![Image](https://github.com/user-attachments/assets/6738901b-6a52-4726-9293-964ba2b5b1a8)

Step 7: Creating the DAX measures for further analysis. 

#### DAX Measures Created

- Total Sales ( Actual )
- Total Sales ( Target )
- Sales Variance 
- Sales Variance %
- YTD Sales ( Actual )
- YTD Sales ( Target )
- YTD Variance 
- YTD Variance %
(YTD - Year to Date )

Special Measures;
- Count of Months when Sales Target achieved
- Title for Actual vs Target sales chart
- Data label for Variance %

The DAX measures have been stored in a separate Measure Table for each of the platforms.

![Image](https://github.com/user-attachments/assets/791e02a4-6e63-40ec-b949-b42f4fe7f95c)

#### Significant DAX Measures:

- YTD Measures,
[ YTD Actual Sales = CALCULATE([Total Sales Actuals], DATESYTD('Calendar'[Date])) ]

[ YTD Target Sales = CALCULATE([Total Sales Target], DATESYTD('Calendar'[Date])) ]

[ YTD Variance = CALCULATE([Variance],DATESYTD('Calendar'[Date])) ]


-  Count of Months when Sales Target achieved

![Image](https://github.com/user-attachments/assets/7e3e6d66-f320-4843-b87d-0788111e2dc5)

- Title for Actual vs Target sales chart

![Image](https://github.com/user-attachments/assets/558dff4a-c3d5-4323-b3ea-6915f6692b27)

- Data label for Variance %

![Image](https://github.com/user-attachments/assets/61338760-d205-4e99-8932-20dc05dfde06)

Step 8: Creating Data Visualization at the Report View tab. 

### Report Page 

![Image](https://github.com/user-attachments/assets/ca5e6fc1-e77b-400f-b9cd-055eecb82411)

#### Section 1: KPIs

In this section the KPIs used are,
- Actual Sales 
- Target Sales
- Variance Amount
- Variance % *

Every card has the YTD value as the reference for the total value. 

![Image](https://github.com/user-attachments/assets/f1a5a276-be7f-410e-815d-0d7bec9292d0)

#### Section 2: Salesperson Performance

This section is a table showing the value of the KPI's for each of the sales persons. 

Along with that a column has been used to show the Actual Sales Trend over the time period. 

![Image](https://github.com/user-attachments/assets/d92dca52-bffe-4944-9583-fb4f37009f49)

The sales trend visualization has been created using the Sparkline feature of Power BI. Also, a marker has been added to the highest value of the trend.

![Image](https://github.com/user-attachments/assets/d48bb9e8-4de0-4c19-ada1-2725f2c18732)

At the Variance % column a visual indicator has been added to show if the Actual Sales is more or less than the Target Sales value. 

*This has been done using the data label we created using the DAX Measure " Data label for Variance % " earlier.

A DrillThrough page has been added to give a quick view, in how many months a sales person has met the target. 

#### Section 3: Actual vs Target Sales Trend

![Image](https://github.com/user-attachments/assets/4ef8a90c-881f-4d9b-b2a4-f6f0595788aa)

In this section Column Chart has been used to compare Actual and Target sales. 

The data value of the Actual Sales column has been marked using the Variance Label. As seen on the image below, 

![Image](https://github.com/user-attachments/assets/5b424b00-9cba-46ba-8760-8cfc57f49c3a)

The Title of this chart has been created using the DAX function " Title for Actual vs Target sales chart ". 

It shows, for how many months Candy Land has achieved the target out of the total observation time. 

![Image](https://github.com/user-attachments/assets/d4af4847-69fc-498c-add5-70425418dd1b)

#### Section 4: Visual Narrative

![Image](https://github.com/user-attachments/assets/2bcddbce-327e-4d39-91af-81b6767ddf5e)

This section has been created using the Narrative option under the Insert menu. 

This presents a summarized version of the report.

#### Section 5: Product Slicer 

![Image](https://github.com/user-attachments/assets/737ce283-bd39-4985-a7f7-aca5c91957ec)

This slicer updates the whole report visuals and shows the data as per the selected product. 

## Insights

#### Insight 1. 

Out of 25 sales persons, 11 salesperson have met the Target Sales, 

- Barr Faughny
- Dennison Crosswaite
- Oby Sorrel
- Kaine Padly
- Beverie Moffet
- Curtis Advani
- Gigi Bohling
- Kelci Walkden
- Roddy Speechly
- Karlen McCaffrey
- Jan Morforth

#### Insight 2
Gunar Cockshoot who sells the product Yummies has made the highest sales among all, still he was 3% short from the Target Sales.

Gunar has met the target 7 out of 14 months. 

His highest sales was in January, 2023 and the lowest one was in November, 2023.

#### Insight 3

Kanine Padly who sells the product Delish, made sales 9% higher than the Target Sales value.

She/he excited the Target for 9 times in the total time period. 

It should be mentioned that she had the lowest sales target among all. 

Marney O'Breen who sells the product Jucies, made sales 11.6% lower than the Target Sals value. 

She excited the Target sales value only once in the total time period.

It should be mentioned that she had the highest sales target among all. 

#### Insight 4

The total observation period is 14 months. The salesperson who has met the overall target assigned to him/her has achieved the target for greater than or equal to 4 months. 

On the other hand the salesperson who has not met the overall target, has met the Target Sales numbers in less than or equal to 4 months.

#### Insight 5

The top 9 salespeople in terms of highest Target Sales number have not met the target. 

On the other hand the bottom 5 salespeople in terms of lowest Target Sales number have met the target.

#### Note: 
- As I don't have a paid subscription to Power BI Service, I couldn't share the report here at GitHub. 
- I am uploading the pbix file, for your ease of understanding. 
