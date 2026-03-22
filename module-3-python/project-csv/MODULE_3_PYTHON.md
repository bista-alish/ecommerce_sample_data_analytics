# MODULE 3: PYTHON STREAMLIT DASHBOARD

Time: 1-2 hours

## Business Requirements

The executive team wants an interactive dashboard they can use to explore sales data. Your task is to:

1. Load the sales data into a web application
2. Display key metrics at a glance
3. Create visualizations showing:
   - Product performance comparison
   - Monthly sales trends
   - Regional distribution
4. Make it interactive so they can explore the data themselves

Build this as a Streamlit web app they can access through their browser.

---

## Detailed Task Breakdown

### Part 1: Setup Environment

**Step 1: Install Required Packages**

Install streamlit, pandas, seaborn, and matplotlib.

**Step 2: Create Project Structure**

Create a folder with app.py and a data subfolder containing sales_data.csv.

---

### Part 2: Build the Dashboard

**Step 3: Import Libraries and Load Data**

Set up your Python file with necessary imports and a function to load the CSV data.

**Step 4: Display Key Metrics**

Create three metric cards showing Total Revenue, Total Sales, and Average Sale.

**Step 5: Create Product Revenue Visualization**

Build a horizontal bar chart using Seaborn showing revenue by product.

**Step 6: Create Monthly Trend Visualization**

Build a line chart showing monthly sales trends.

**Step 7: Create Regional Distribution Visualization**

Build a pie chart showing revenue distribution by region.

**Step 8: Add Raw Data Table**

Display the raw data in a table at the bottom.

---

### Part 3: Run and Test

**Step 9: Launch the Dashboard**

Run the Streamlit application and verify all components display correctly.

---

### Part 4: Optional Enhancement

**Step 10: Add Interactive Filters**

Add sidebar filters to allow filtering by product and region.

---

## Deliverable

Save your work as **app.py**

Your application should include:
- Three metric cards at the top
- Three visualizations (bar chart, line chart, pie chart)
- Raw data table
- Optional: Interactive filters

---

## Need Help?

### Part 1: Setup Environment

**Step 1: Install Required Packages**

Open your terminal/command prompt and run:

```bash
pip install streamlit pandas seaborn matplotlib
```

**Step 2: Create Project Structure**

Create this folder structure:
```
dashboard/
├── app.py
└── data/
    └── sales_data.csv
```

Copy your sales_data.csv file into the data folder.

### Part 2: Build the Dashboard

**Complete code for app.py:**

```python
import streamlit as st
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Configure page
st.set_page_config(page_title="Sales Dashboard", layout="wide")

# Title
st.title("Sales Performance Dashboard")

# Load data
@st.cache_data
def load_data():
    df = pd.read_csv('data/sales_data.csv')
    df['Date'] = pd.to_datetime(df['Date'])
    return df

df = load_data()

# Display key metrics
st.header("Key Metrics")

col1, col2, col3 = st.columns(3)

with col1:
    total_revenue = df['Total'].sum()
    st.metric("Total Revenue", f"${total_revenue:,.0f}")

with col2:
    total_sales = len(df)
    st.metric("Total Sales", f"{total_sales:,}")

with col3:
    avg_sale = df['Total'].mean()
    st.metric("Average Sale", f"${avg_sale:.0f}")

st.divider()

# Visualization 1: Sales by Product
st.header("Revenue by Product")

product_revenue = df.groupby('Product')['Total'].sum().sort_values(ascending=True)

fig1, ax1 = plt.subplots(figsize=(10, 6))
sns.barplot(x=product_revenue.values, y=product_revenue.index, palette='viridis', ax=ax1)
ax1.set_xlabel('Revenue ($)')
ax1.set_ylabel('Product')
ax1.set_title('Revenue by Product')
st.pyplot(fig1)

st.divider()

# Visualization 2: Monthly Sales Trend
st.header("Monthly Sales Trend")

df['Month'] = df['Date'].dt.to_period('M').astype(str)
monthly_sales = df.groupby('Month')['Total'].sum()

fig2, ax2 = plt.subplots(figsize=(10, 6))
monthly_sales.plot(kind='line', marker='o', ax=ax2)
ax2.set_xlabel('Month')
ax2.set_ylabel('Revenue ($)')
ax2.set_title('Monthly Revenue Trend')
ax2.grid(True, alpha=0.3)
plt.xticks(rotation=45)
st.pyplot(fig2)

st.divider()

# Visualization 3: Sales by Region
st.header("Sales by Region")

region_sales = df.groupby('Region')['Total'].sum()

fig3, ax3 = plt.subplots(figsize=(8, 8))
colors = sns.color_palette('pastel')
ax3.pie(region_sales.values, labels=region_sales.index, autopct='%1.1f%%', 
        colors=colors, startangle=90)
ax3.set_title('Revenue Distribution by Region')
st.pyplot(fig3)

st.divider()

# Show raw data
st.header("Raw Data")
st.dataframe(df, use_container_width=True)
```

### Part 3: Run and Test

**Step 9: Launch the Dashboard**

In your terminal, navigate to your dashboard folder and run:

```bash
streamlit run app.py
```

Your browser should automatically open to http://localhost:8501

### Part 4: Optional Enhancement

**Step 10: Add Interactive Filters**

If you want to add filters, add this code right after the `df = load_data()` line:

```python
# Add sidebar filters
st.sidebar.header("Filters")

# Product filter
products = st.sidebar.multiselect(
    "Select Products",
    options=df['Product'].unique(),
    default=df['Product'].unique()
)

# Region filter
regions = st.sidebar.multiselect(
    "Select Regions",
    options=df['Region'].unique(),
    default=df['Region'].unique()
)

# Apply filters
df = df[df['Product'].isin(products) & df['Region'].isin(regions)]
```

Now users can filter the dashboard by product and region!
