# MODULE 4: POWER BI DASHBOARD

Time: 1-2 hours

## Business Requirements

Management wants a professional BI dashboard they can use in meetings. Your task is to:

1. Import the sales data into Power BI
2. Create calculated measures for key metrics
3. Build visualizations showing:
   - Top performing products
   - Sales trends over time
   - Regional performance
4. Add filters so they can drill down into specific time periods
5. Make it look professional and easy to understand

---

## Detailed Task Breakdown

### Part 1: Import and Prepare Data

**Step 1: Import CSV File**

Open Power BI Desktop and import sales_data.csv.

**Step 2: Transform Data Types**

Use Power Query Editor to ensure all columns have correct data types.

**Step 3: Apply Changes**

Close Power Query and apply the transformations.

---

### Part 2: Create DAX Measures

**Step 4: Create Total Revenue Measure**

Create a DAX measure that sums all sales.

**Step 5: Create Total Sales Measure**

Create a DAX measure that counts all transactions.

**Step 6: Create Average Sale Measure**

Create a DAX measure that calculates average transaction value.

---

### Part 3: Build Dashboard Visualizations

**Step 7: Add KPI Cards**

Create three card visuals showing your measures at the top of the page.

**Step 8: Create Product Revenue Chart**

Build a clustered bar chart showing revenue by product.

**Step 9: Create Monthly Trend Chart**

Build a line chart showing sales over time.

**Step 10: Create Regional Distribution Chart**

Build a donut chart showing revenue by region.

**Step 11: Arrange Visuals**

Position all visuals in a clean, organized layout.

---

### Part 4: Add Interactivity

**Step 12: Add Date Slicer**

Create a slicer for filtering by date range.

**Step 13: Add Product Filter**

Create a dropdown slicer for filtering by product.

**Step 14: Test Interactions**

Verify that clicking on visuals filters other components correctly.

---

### Part 5: Format and Polish

**Step 15: Apply Theme**

Choose and apply a professional theme to your dashboard.

**Step 16: Format Visuals**

Clean up gridlines, add clear titles, and format numbers properly.

**Step 17: Add Dashboard Title**

Add a text box with your dashboard title.

---

## Deliverable

Save your file as **sales_dashboard.pbix**

Your dashboard should include:
- Three KPI cards
- Bar chart (products)
- Line chart (monthly trend)
- Donut chart (regions)
- Two slicers (date and product)
- Professional formatting

---

## Need Help?

### Part 1: Import and Prepare Data

**Step 1: Import CSV File**

1. Open Power BI Desktop
2. Click "Get Data" on the Home ribbon
3. Select "Text/CSV"
4. Navigate to and select sales_data.csv
5. Click "Open"
6. Preview window will appear

**Step 2: Transform Data Types**

1. Click "Transform Data" to open Power Query Editor
2. Check the data type icon next to each column name:
   - SaleID: Should be Whole Number (123 icon)
   - Date: Should be Date (calendar icon)
   - Product: Should be Text (ABC icon)
   - Quantity: Should be Whole Number
   - Price: Should be Decimal Number (1.2 icon)
   - Total: Should be Decimal Number
   - Region: Should be Text
3. If any are wrong, click the icon and select the correct type

**Step 3: Apply Changes**

1. Click "Close & Apply" in the top left
2. Wait for data to load

### Part 2: Create DAX Measures

Click "New Measure" on the Home ribbon for each:

**Step 4: Create Total Revenue Measure**

```
Total Revenue = SUM(sales[Total])
```

Press Enter to save.

**Step 5: Create Total Sales Measure**

```
Total Sales = COUNTROWS(sales)
```

Press Enter to save.

**Step 6: Create Average Sale Measure**

```
Average Sale = DIVIDE([Total Revenue], [Total Sales], 0)
```

Press Enter to save.

### Part 3: Build Dashboard Visualizations

**Step 7: Add KPI Cards**

1. From Visualizations pane, click the "Card" icon (do this 3 times)
2. For first card: From Fields pane, drag "Total Revenue" measure to the card
3. For second card: Drag "Total Sales" measure
4. For third card: Drag "Average Sale" measure
5. Resize and position them across the top of the page

Format the cards:
- Click on each card
- Go to Format visual (paint roller icon)
- Expand "Callout value"
- Set Display units to "None"
- For revenue cards: Format > Callout value > change to Currency format

**Step 8: Create Product Revenue Chart**

1. Click blank space on canvas
2. From Visualizations, click "Clustered bar chart"
3. From Fields pane:
   - Drag "Product" to Y-axis
   - Drag "Total Revenue" to X-axis
4. Click on visual, then Format visual (paint roller)
5. Expand "Title"
6. Change text to "Revenue by Product"

**Step 9: Create Monthly Trend Chart**

1. Click blank space on canvas
2. From Visualizations, click "Line chart"
3. From Fields pane:
   - Drag "Date" to X-axis (it will create a date hierarchy)
   - Drag "Total Revenue" to Y-axis
4. Format visual > Title: "Monthly Sales Trend"
5. Format visual > Data labels: Turn on

**Step 10: Create Regional Distribution Chart**

1. Click blank space on canvas
2. From Visualizations, click "Donut chart"
3. From Fields pane:
   - Drag "Region" to Legend
   - Drag "Total Revenue" to Values
4. Format visual > Detail labels: Turn on
5. Format visual > Title: "Revenue by Region"

**Step 11: Arrange Visuals**

Drag and resize your visuals to create a clean layout:
- KPI cards at top
- Charts below in organized rows

### Part 4: Add Interactivity

**Step 12: Add Date Slicer**

1. Click blank space on canvas
2. From Visualizations, click "Slicer"
3. From Fields pane, drag "Date" to the slicer
4. Click the dropdown arrow in the slicer header
5. Select "Between" (allows date range selection)
6. Position on left side or top

**Step 13: Add Product Filter**

1. Click blank space on canvas
2. From Visualizations, click "Slicer"
3. From Fields pane, drag "Product" to the slicer
4. Click dropdown in slicer > Select "Dropdown" style
5. Format visual > Slicer settings > Selection > Turn on "Show Select All"
6. Format visual > Slicer settings > Selection > Multiple selection: On
7. Position near date slicer

**Step 14: Test Interactions**

Try these:
- Click on a bar in the product chart (other visuals should highlight)
- Select a date range in the date slicer (all visuals should filter)
- Select products in the dropdown (dashboard should update)
- Click on a region slice (other visuals should respond)

### Part 5: Format and Polish

**Step 15: Apply Theme**

1. Go to View tab on ribbon
2. Click "Themes"
3. Select a theme (try "Executive" or "Minimal")

**Step 16: Format Visuals**

For each visual:
1. Click on it
2. Go to Format visual
3. Expand "Grid" section
4. Turn off gridlines (if visible)
5. Ensure titles are visible
6. Check number formatting is correct

**Step 17: Add Dashboard Title**

1. Go to Insert tab
2. Click "Text box"
3. Type "Sales Performance Dashboard"
4. Increase font size to 24-28
5. Make it bold
6. Position at very top of page
7. Resize to span width of dashboard
