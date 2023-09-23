# Head Rest Ltd Retail Company Performance Analysis
Our data belongs to a fictional retail company called Head Rest Ltd. Head Rest Ltd. sells beds and sleep-related accessories.The company has several stores, each of which has a home manager.Each store sells four brands of products, including our own brand, Head Rest Beds.Each brand offers products in the categories of mattresses,bed frames, pillows and bed linen Managers earn commissions based on sales and their time in service.

_**Disclaimer**_: All datasets and reports do no represent any company, institution, or country, but just a dummy dataset to demonstrate the capabilities of Power Pivot in Excel.

## Problem Statement
- Which State had the most sales?
- which product category had the most sales?
- which product category had the most YoY Sales Growth?
- which month of the year is sales at an all time high?
- Which brand had the most sales?
- Which brand had the most Yoy Sales Growth?
- Which month had the most sales?

## Skills / Concepts Demonstrated
The following Power BI Features were incorporated:

- Bookmarking,
- Data Modelling,
- Dax,
- Quick Measures,
- Power Pivot
- Page Navigation,
- Filters (Timelines and Slicers),

## Tables in the data model
- Product Dimension Table 
- Sales Fact Table
- Commission Dimension Table
- Store Dimension Table
- Date Dimension Table
- Manager Dimension Table

## Modelling
The Data was manually modelled, it was a hybrid schema.
![](https://github.com/CoyoteStark25/Profit_and_Loss_Report-Power_BI_Project/blob/main/Images/DataModel.PNG)

## Visualization
The Report Comprises of 3 Pages:
### A Sample of the first Page
![](https://github.com/CoyoteStark25/Profit_and_Loss_Report-Power_BI_Project/blob/main/Images/ReportPage1.PNG)

## Some calculated fields include
Units:=sum([Units Sold])
Store Size=switch(Dim_Stores[Store Type],"SM","SMALL","MED","MEDIUM","WAREHOUSE")
MarginDollars=Sales[Units Sold]*Sales[UnitPrice]*Sales[Margin]
MarginAmt:=sum(Sales[MarginDollars])

SumSales:=sumx(Sales,[Units Sold]*[UnitPrice])
Color=SWITCH([ColorCode],”W”,”White”,”B”,”Blue”,”R”,”Red”,”S”,”Silver”,”Other”)
SalesDays:=DISTINCTCOUNT(Sales[DateID])
SalesPerDay:=[Sales]/[SalesDays]

## some Dax Time Intelligence Functions
SalesPY:=CALCULATE([Sales], SAMEPERIODLASTYEAR(Dim_Dates[Date]))
SalesPerDayYTD:=calculate([SalesPerDay],DATESYTD(Dim_Dates[Date]))


## Some insights from the Analysis
1.	The gross profit margin for 2019 performed better than that of the previous year by a little over 1%.
2.	Sales were at an all-time high in 2019 compared to that of the last two years.
3.	They did not meet their target sales, though, missed it by roughly 0.2bn.
4.	The State of Texas had the most sales of 216 million plus.
5.	A further breakdown of sales by department and product group showed that clothing brought in the most sales overall.
6.	For the past 3 years sales seem to see a big spike around November, specifically around the 22nd -24th 
7.	Upon grouping the department and groups together to get deeper insights into the sales data, it showed that tools: Garage had the most Sales YOY Growth percentage.
8.	Sales shared by group and department show that kitchen: Kitchen utensils had the most singular contribution to sales, although clothing had the most overall sales contribution.
9.	The united states had more store outlets than Canada.
10.	For the electronics category, Laptops seemed to have the most sales.
11.	Women’s clothing sold more than male clothing.
