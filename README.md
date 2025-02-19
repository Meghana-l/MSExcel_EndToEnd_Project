## Coffee Sales Interactive Dashboard using Excel
This Excel dashboard provides a user-friendly way to analyze coffee sales data.  Its interactive design allows users to filter the data by several key criteria, including time period, coffee roast type, cup size, and customer loyalty status.  These filters enable users to drill down into the data and explore specific trends and customer preferences.

Moreover, the dashboard visually represents the data through a combination of charts.  A line chart displays total sales over time, allowing users to easily see sales growth or decline.  Bar charts visualize sales performance by country and highlight top-performing customers.  By presenting complex sales information in a clear and concise visual format, the dashboard empowers users to identify key trends, assess overall sales performance, and make data-driven decisions to optimize their coffee sales strategies and maximize revenue.

### Steps Followed
- Step 1 : Get the dataset (excel file). The data file has been uploaded (coffeeOrdersData.xlsx)

- Step 2 : The data file contains 3 worksheets containing Orders, Customers and Products.
   Gather the data from Customers and Products into the Orders worksheet. Add the columns Customer Name, Email, Country from the Customers worksheet and the columns Coffee Type, Roast Type, Size, Unit Price from the Products worksheet.

- Step 3 : Use XLOOKUP function for getting columns from the Customers worksheet into Orders sheet. Select the first cell under each of the columns and type-in the function. Press Enter and populate all the columns to fill in all the values.
For Customer Name column 

        =XLOOKUP(C145,customers!$A:$A,customers!$B:$B,,0)
 To get the Email column

        =IF(XLOOKUP(C145,customers!$A:$A,customers!$C:$C,,0)=0,"",
        XLOOKUP(C145,   customers!$A:$A,customers!$C:$C,,0))
 To get the Country column

       =XLOOKUP(C145,customers!$A:$A,customers!$G:$G,,0)

- Step 4 : Use the INDEX function to get the Coffee Type, Roast Type, Size, Unit Price columns into the Orders Table.
- Step 5 : Select the first cell under the Coffee Type Column and type-in the INDEX function. Use the MATCH function to match the row number and column number between the Orders and Products table. 

        =INDEX(products!$A$1:$G$49,MATCH(orders!$D145,products!$A:$A,0),
        MATCH(orders!I$1,products!$A$1:$G$1,0))
- Step 6 : Now Populate the rest of the columns horizontally; Double-click at the bottom right-corner of the first cells to populate the entire column fields.            
- Step 7 :Add a column 'Sales'. Sales is calculated as Unit Price* Quantity.
- Step 8 : Add another column 'Coffee Type Name' which contains the full name of the coffee type, and not the abbreviation. Use IF function for this.

        =IF(I145="Rob","Robusta",IF(I145="Exc","Excelsa",
        IF(I145="Ara","Arabica",IF(I145="Lib","Liberica",""))))

- Step 9 : Do the same for 'Roast Type Name' column.

        =IF(J145="M","Medium",IF(J145="L","Light",IF(J145="D","Dark","")))

- Step 10 : Finally, add the 'Loyalty Card' column and use the XLOOKUP fn to get the values from the Customers table.

        =XLOOKUP([@[Customer ID]],customers!$A:$A,customers!$I:$I,,0)

- Step 11 : Format the data, that is, Size should be in kg and change format for Unit Price and Sales to USD(Currency).
Also, select the entire data range and remove duplicates (in the Data Tab)

- Step 12 :Now, convert the Orders sheet into a table so that we can create Pivot Table and charts. Click on any cell in the range and press [Ctrl + T] on your key-board. Name table as 'Orders'. 
Then insert a Pivot Table, and select range as Orders. Name the New worksheet as TotalSales.
- Step 13 : Select the Pivot Table and add the fields into rows, values, columns accordingly.
![Image](https://github.com/user-attachments/assets/342b1761-7187-4956-95a1-bba4f02e0f0a)
##### ...contains more rows.
       
- Step 14 : From the pivot table create Line chart, slicers, time line and bar charts. Format them accordingly.


- Step 15 : Add a new worksheet, and name it "CoffeeSalesDashboard". Gather all the charts and visuals and arrange them in this worksheet and make it look clean.
Remove grid lines and Dashboard is ready!

![Image](https://github.com/user-attachments/assets/38434acb-0a6c-4d0d-86cd-6d5fdb6b3a36)






   
