# Internet Service Customer Churn Analysis (Excel)

<p>In this analysis, we will explore the Customer Churn dataset to understand the factors that lead to customers discontinuing their internet service. We will also offer recommendations on how to reduce churn and retain customers.</p>

<ol>
  <li><b>Is Subscription Type correlated with customer churn?</b>
      <p>Determining which subscription type is more likely to result in customer churn.</p>
  </li>
  <li><b>Which Contract Length leads to higher customer churn?</b>
    <p>Identifying the contract length that has the highest rate of customer churn.</p>
  </li>
  <li><b>How much revenue is lost due to customer churn?</b>
      <p>Analyzing the financial impact of customer churn on company sales.</p>
  </li>
  <li><b>Is payment delay related to customer churn?</b>
    <p>Analyzing the relationship between payment delays and customer churn.</p>
  </li>
  <li><b>Is there any correlation between Gender, Age, and Customer Churn?</b>
    <p>Identifying the correlation between gender, age, and customer churn.</p>
  </li>
  <li><b>Which Tenure category is more likely to result in customer churn?</b>
    <p>Identifying the tenure category that is most likely to experience customer churn.</p>
  </li>
</ol>

<p><b>Dataset Source: </b>https://www.kaggle.com/datasets/muhammadshahidazeem/customer-churn-dataset/data</p>
 
## Cleaning the dataset
### Step 1: Understand the dataset

<p>The dataset contains 64374 records of customer realated data. <br>There are 11 columns of data as below: </p>

<ol>
  <li><b>CustomerID</b>: A unique identifier for each customer. This helps to distinguish each customer individually.</li>
  <li><b>Age</b>: The age of the customer.</li>
  <li><b>Gender</b>: The gender of the customer (e.g., Male, Female).</li>
  <li><b>Tenure</b>: The length of time (in months) that the customer has been using the service.</li>
  <li><b>Support Calls</b>: The number of times the customer has contacted customer support. This might indicate how much assistance the customer needs or how many issues they have encountered.</li>
  <li><b>Payment Delay</b>: Indicates if the customer has delayed payments and possibly the frequency or extent of these delays.</li>
  <li><b>Subscription Type</b>: The type of subscription the customer has chosen. This could include different service plans or levels (e.g., Basic, Premium).</li>
  <li><b>Contract Length</b>: The duration of the contract the customer has agreed to (e.g., 1 year, 2 years).</li>
  <li><b>Total Spend</b>: The total amount of money the customer has spent on the service over their tenure.</li>
  <li><b>Last Interaction</b>: The last time the customer interacted with the service or company. This could be the last purchase, login, or contact with customer support.</li>
  <li><b>Churn</b>: This is the key column indicating whether the customer has stopped using the service or product. It is typically a binary value (e.g., Yes/No, 1/0) where "Yes" or "1" indicates that the customer has churned (left the service), and "No" or "0" indicates that the customer is still active.</li>
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
