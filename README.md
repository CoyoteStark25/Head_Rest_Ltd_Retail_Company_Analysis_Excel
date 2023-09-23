# Head Rest Ltd Retail Company Analysis
Our data belongs to a fictional retail company called Head Rest Ltd. Head Rest Ltd. sells beds and sleep-related accessories.The company has several stores, each of which has a home manager.Each store sells four brands of products, including our own brand, Head Rest Beds.Each brand offers products in the categories of mattresses,bed frames, pillows and bed linen Managers earn commissions based on sales and their time in service.

## Tables in the data model
- Product Dimension Table 
- Sales Fact Table
- Commission Dimension Table
- Store Dimension Table
- Date Dimension Table
- Manager Dimension Table

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
