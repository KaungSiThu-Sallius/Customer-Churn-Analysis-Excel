# Customer-Churn-Analysis-Excel

<p>In this analysis, we will examine the Customer Churn dataset to gain insights into the factors that cause customers to unsubscribe from the service. Additionally, we will provide recommendations on how to prevent churn.</p>

<ol>
  <li><b>Does Subsription Type is correlated with customer churn?</b>
      <p>Identifying which subscription type is more likely to cause customer churn.</p>
  </li>
  <li><b>Which Contract Length is cause more customer churn?</b>
    <p>Identifying type of Contract Length with is more customer churn.</p>
  </li>
  <li><b>How much is is lost to company due to customer churn?</b>
      <p>Analyzing sales that effect due to customer churn.</p>
  </li>
  <li><b>Is payment delay realted with customer churn?</b>
    <p>Asnalysing customer churn by payment delay</p>
  </li>
  <li><b>Which brand is the most popular?</b>
    <p>Evaluating brand popularity by analyzing sales data across different brands.</p>
  </li>
</ol>

 <p><b>Dataset Source: </b>https://www.kaggle.com/datasets/muhammadshahidazeem/customer-churn-dataset/data</p>
 
## Cleaning the dataset
### Step 1: Understand the dataset

<p>The dataset contains 5096 records of sales transactions between 11/01/2020 - 31/12/2022. <br>There are 14 columns of data as below: </p>

<ol>
  <li><b>Order_Number</b>: Unique identifier for each order.</li>
  <li><b>State_Code</b>: The code representing the state where the order was placed.</li>
  <li><b>Customer_Name</b>: The name of the customer who placed the order.</li>
  <li><b>Order_Date</b>: The date when the order was placed.</li>
  <li><b>Status</b>: The current status of the order (e.g., Order, Processing, Shipped, Delivered).</li>
  <li><b>Product</b>: The name or identifier of the product sold.</li>
  <li><b>Category</b>: The category to which the product belongs.</li>
  <li><b>Brand</b>: The brand of the product.</li>
  <li><b>Cost</b>: The cost incurred by the business to acquire or produce the product.</li>
  <li><b>Sales</b>: The revenue earned from selling the product.</li>
  <li><b>Quantity</b>: The number of units sold in the order.</li>
  <li><b>Total_Cost</b>: The total cost for the quantity sold (Cost * Quantity).</li>
  <li><b>Total_Sales</b>: The total revenue for the quantity sold (Sales * Quantity).</li>
  <li><b>Assigned Supervisor</b>: The supervisor responsible for the order.</li>
</ol>

<p>Firstly, I converted the cells into a table by using <kbd>Cmd</kbd> + <kbd>T</kbd> in Excel.</p>

### Step 2: Check for Duplicates Records

<p>After understanding the dataset, I check for any duplicates first by Excel built-in functionality, "Remove Duplicates".</p>

### Step 3: Check for Any Blanks or Irregular Values in Records

<p>By using conditional formatting, I highlighted the blank cells. Since the highlighted rows were all empty, I deleted them. I didn't find any blank cells or irregular values.</p>

## Preparing the dataset
### Creating new columns

<p>I extracted the unique state codes from the State_Code column using the UNIQUE formula. Next, I searched for the full names corresponding to these state codes and created a new sheet to map state codes to state names. Then, using <b>VLOOKUP</b> in the original Excel analysis sheet, I created a new column called State_Name and filled it with data obtained from the <b>VLOOKUP</b> formula.</p>

<p>Afterward, I created a new column called Month by using the <b>TEXT</b> formula on the Order_Date column. Then, I added another new column called Profit by subtracting the Total Cost column from the Total Sales column.</p>

## Define Metrics for Dashboard
<p>We create the following pivot tables to answer our business questions.</p>

### Metric 1: Total Sales
<b>Values:</b> Total Sales (By Sum)

### Metric 2: Total Profit
<b>Values:</b> Profit (By Sum)

### Metric 3: Top 5 Best Selling Products by Total Sales
<b>Values:</b> Total Sales (By Sum)<br>
<b>Rows:</b> Product<br>
<b>Filter:</b> Top 5 Prodcuts<br>

### Metric 4: Best Selling Categories by Count
<b>Values:</b> Quantity (By Sum)<br>
<b>Rows:</b> Category<br>

### Metric 5: Monthly Total Sales by Category
<b>Values:</b> Total Sales (By Sum)<br>
<b>Rows:</b> Month<br>
<b>Columns:</b> Category<br>

### Metric 6: Total Sales by States
<b>Values:</b> Total Sales (By Sum)<br>
<b>Rows:</b> State_Name<br>

### Metric 7: Total Sales Precentage by Brand
<b>Values:</b> Total Sales (By Sum)<br>
<b>Rows:</b> Brand<br>

### Metric 8: Top 5 Most Profitable Products
<b>Values:</b> Profit (By Sum)<br>
<b>Rows:</b> Product<br>

## Creating Charts for Certain Metrics
