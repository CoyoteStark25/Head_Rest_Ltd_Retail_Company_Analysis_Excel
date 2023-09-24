# Head Rest Ltd Retail Company Performance Analysis
![HeadRestBedPic](https://github.com/CoyoteStark25/Head_Rest_Ltd_Retail_Company_Analysis_Excel/assets/77941966/2d0151c0-dc3a-443a-af0b-9b5605dc3163)

The data belongs to a fictional retail company called Head Rest Ltd. Head Rest Ltd. sells beds and sleep-related accessories.The company has several stores, each of which has a home manager.Each store sells four brands of products, including our own brand, Head Rest Beds.Each brand offers products in the categories of mattresses,bed frames, pillows and bed linen Managers earn commissions based on sales and their time in service.

_**Disclaimer**_: All datasets and reports do not represent any company, institution, or country, but just a dummy dataset to demonstrate the capabilities of Power Pivot in Excel.

## Problem Statement

- Which City had the most sales?
- which product category had the most sales?
- which product category had the most YoY Sales Growth?
- which month of the year is sales at an all time high?
- Which brand had the most sales?
- Which brand had the most Yoy Sales Growth?
- Which month had the least sales?
- Which city sold the least no of units?

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
The Data was manually modelled, it was a Star schema.
![DataModel](https://github.com/CoyoteStark25/Head_Rest_Ltd_Retail_Company_Analysis_Excel/assets/77941966/c1904dde-7b76-4acf-a2f6-32ffeaeb9a32)

## Visualization

The Report Comprises of 2 Pages:
### A Sample of the Business Overview Page
![Business Overview](https://github.com/CoyoteStark25/Head_Rest_Ltd_Retail_Company_Analysis_Excel/assets/77941966/d86ccf9f-b4d5-459b-9bc4-793d7554cfae)

### A Sample of the Store Performance Page
![Store Performance](https://github.com/CoyoteStark25/Head_Rest_Ltd_Retail_Company_Analysis_Excel/assets/77941966/181bf14d-ab5d-4504-ab50-c8dff06ee227)

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
1.	Las Vegas had the most Sales
2.	Mattress had the most sales
3.	Mattress also had the most YoY Sales growth
4.	Sales were at an all time high during the month of December, this was consistent across 2018 to 2019
5.	Lux Bed was the brand with the most sales
6.	Ocean Sleep had the most YoY sales growth
7.	The month of june had the least sales and this was consistent across 2018 and 2019
8.	Denver sold the least number of units.
