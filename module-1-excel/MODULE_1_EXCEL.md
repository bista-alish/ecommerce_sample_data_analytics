# MODULE 1: EXCEL DATA ANALYSIS

Time: 1-2 hours

## Business Requirements

You are a data analyst at a retail company. Your manager has asked you to:

1. Clean the sales data and fix any data quality issues
2. Analyze which products are generating the most revenue
3. Identify trends in sales over the year
4. Create a simple dashboard showing key metrics

The raw data file is sales_data.csv.

---

## Detailed Task Breakdown

### Part 1: Load and Clean Data

**Step 1: Open the File**

Open sales_data.csv in Excel and save it as "sales_analysis.xlsx"

**Step 2: Format as Table**

Convert your data range into an Excel table.

**Step 3: Clean Missing Regions**

Some rows have blank Region values. Find them and fill with "Unknown".

**Step 4: Remove Duplicate Rows**

Use Excel's built-in feature to remove any duplicate records.

---

### Part 2: Create Pivot Tables

**Step 5: Create Sales by Product Pivot Table**

Create a pivot table showing total revenue for each product. Sort by revenue (highest first). Format numbers as currency. Create this in a new worksheet named "Sales by Product".

**Step 6: Create Monthly Sales Pivot Table**

Create a pivot table showing total revenue by month. You'll need to group the dates by month. Format as currency. Create this in a new worksheet named "Monthly Sales".

---

### Part 3: Create Charts

**Step 7: Create Product Revenue Chart**

Using your Sales by Product pivot table, create a bar chart showing revenue by product. Title it "Revenue by Product".

**Step 8: Create Monthly Trend Chart**

Using your Monthly Sales pivot table, create a line chart showing the monthly trend. Title it "Monthly Sales Trend".

---

### Part 4: Create Dashboard

**Step 9: Create Dashboard Worksheet**

Create a new worksheet named "Dashboard".

**Step 10: Add Key Metrics**

Add three formulas to calculate:
- Total Revenue (sum of all sales)
- Total Sales (count of transactions)
- Average Sale (average transaction value)

Format these metrics to be large and easy to read.

**Step 11: Add Charts to Dashboard**

Copy both charts to your Dashboard worksheet and arrange them neatly.

**Step 12: Add Dashboard Title**

Add "Sales Analysis Dashboard" as a title at the top.

---

## Deliverable

Save your file as **sales_analysis.xlsx**

Your file should contain:
- Cleaned data with no duplicates or blank regions
- Two pivot tables (by product and by month)
- Two charts (bar chart and line chart)
- A dashboard with metrics and visualizations

---

## Need Help?

### Part 1: Load and Clean Data

**Step 1: Open the File**

1. Open Microsoft Excel
2. Go to File > Open > sales_data.csv
3. Save the file as "sales_analysis.xlsx"

**Step 2: Format as Table**

1. Select all data (click on cell A1, then press Ctrl+Shift+End)
2. Go to Home tab > Format as Table
3. Choose any table style
4. Make sure "My table has headers" is checked
5. Click OK

**Step 3: Clean Missing Regions**

1. Click on the Region column header
2. Go to Data tab > Filter
3. Click the dropdown arrow in Region column
4. Uncheck "Blanks" to see rows with missing regions
5. Select all blank cells in the Region column
6. Type "Unknown" and press Ctrl+Enter (fills all selected cells)
7. Remove the filter

**Step 4: Remove Duplicate Rows**

1. Select all data (Ctrl+A or click anywhere in the table)
2. Go to Data tab > Remove Duplicates
3. Make sure all columns are checked
4. Click OK
5. Excel will tell you how many duplicates were removed

### Part 2: Create Pivot Tables

**Step 5: Create Sales by Product Pivot Table**

1. Click anywhere in your data table
2. Go to Insert tab > PivotTable
3. Select "New Worksheet"
4. Click OK
5. Drag "Product" to Rows area
6. Drag "Total" to Values area (it should show "Sum of Total")
7. Right-click any number in the Values column
8. Select "Number Format"
9. Choose "Currency" with 0 decimal places
10. Click OK
11. Click the dropdown arrow next to "Row Labels"
12. Select "More Sort Options"
13. Choose "Descending (Z to A)"
14. Select "Sum of Total"
15. Click OK
16. Rename the worksheet to "Sales by Product"

**Step 6: Create Monthly Sales Pivot Table**

1. Go back to your data sheet
2. Insert > PivotTable > New Worksheet
3. Drag "Date" to Rows area
4. Drag "Total" to Values area
5. Right-click any date in the pivot table
6. Select "Group"
7. Choose "Months"
8. Click OK
9. Right-click numbers and format as currency
10. Rename the worksheet to "Monthly Sales"

### Part 3: Create Charts

**Step 7: Create Product Revenue Chart**

1. Go to your "Sales by Product" sheet
2. Click anywhere in the pivot table
3. Go to Insert tab > Bar Chart > Clustered Bar
4. Click on the chart title and change it to "Revenue by Product"
5. Resize the chart to make it larger

**Step 8: Create Monthly Trend Chart**

1. Go to your "Monthly Sales" sheet
2. Click anywhere in the pivot table
3. Go to Insert tab > Line Chart
4. Click on the chart title and change it to "Monthly Sales Trend"
5. Resize the chart to make it larger

### Part 4: Create Dashboard

**Step 9: Create Dashboard Worksheet**

1. Insert a new worksheet (click the + icon at the bottom)
2. Rename it to "Dashboard" (right-click the tab)

**Step 10: Add Key Metrics**

In cells B2, B3, and B4, add these formulas:

Cell B2 (Total Revenue):
```
=SUM(Table1[Total])
```

Cell B3 (Total Sales Count):
```
=COUNTA(Table1[SaleID])
```

Cell B4 (Average Sale):
```
=AVERAGE(Table1[Total])
```

Note: Replace "Table1" with your actual table name if it's different.

In cells A2, A3, and A4, add labels:
- A2: "Total Revenue"
- A3: "Total Sales"
- A4: "Average Sale"

Format the metrics:
- Select B2:B4
- Change font size to 18-20
- Make them bold
- Format B2 and B4 as currency (right-click > Format Cells > Currency)

**Step 11: Add Charts to Dashboard**

1. Go to your "Sales by Product" sheet
2. Click on the chart
3. Press Ctrl+C to copy
4. Go to Dashboard sheet
5. Press Ctrl+V to paste
6. Position it below your metrics
7. Repeat for the Monthly Sales chart from the other sheet

**Step 12: Add Dashboard Title**

1. Click on cell A1
2. Type "Sales Analysis Dashboard"
3. Make the font size 20-24
4. Make it bold
5. Merge cells A1:E1 if you want it centered across the top
