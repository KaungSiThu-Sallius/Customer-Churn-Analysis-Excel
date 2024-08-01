# Internet Service Customer Churn Analysis (Excel)

<p>In this analysis, we will explore the Customer Churn dataset to understand the factors that lead to customers discontinuing their internet service. We will also offer recommendations on how to reduce churn and retain customers.</p>

<ol>
  <li>
      <b>Is the difference in LTV between churned and non-churned customers statistically significant?</b>
      <p>Determine how much impact the company can have due to churned customers.</p>
  </li>
  <li><b>Is Subscription Type correlated with customer churn?</b>
      <p>Determining which subscription type is more likely to result in customer churn.</p>
  </li>
  <li><b>Which Contract Length leads to higher customer churn?</b>
    <p>Identifying the contract length that has the highest rate of customer churn.</p>
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
  <li><b>Payment Delay</b>: Indicates how frequently the customer has delayed payments.</li>
  <li><b>Subscription Type</b>: The type of subscription the customer has chosen. This could include different service plans or levels (e.g., Basic, Standard, Premium).</li>
  <li><b>Contract Length</b>: The duration of the contract the customer has agreed to (e.g., 1 year, 2 years).</li>
  <li><b>Total Spend</b>: The total amount of money the customer has spent on the service over their tenure.</li>
  <li><b>Last Interaction</b>: The last time the customer interacted with the service or company. This could be the last purchase, login, or contact with customer support.</li>
  <li><b>Churn</b>: This is the key column indicating whether the customer has stopped using the service or product. In which, "1" indicates that the customer has churned (left the service), and "0" indicates that the customer is still active.</li>
</ol>

<p>Firstly, I converted the cells into a table by using <kbd>Cmd</kbd> + <kbd>T</kbd> in Excel.</p>

### Step 2: Check for Duplicates Records

<p>After understanding the dataset, I check for any duplicates first by Excel built-in functionality, "Remove Duplicates".</p>

### Step 3: Check for Any Blanks or Irregular Values in Records

<p>By using conditional formatting, I highlighted the blank cells. Since the highlighted rows were all empty, I deleted them. I didn't find any blank cells or irregular values.</p>

## Preparing the dataset
### Creating new columns

<p>I added a new column called "Total Count" and filled it with the value 1. This column will help in calculating the churn rate when creating a pivot table.</p>
<p>Next, I categorized the "Age" column into three groups and created a new column called "Age Categories" using the IF formula. The three age categories are "Adolescents," "Middle-aged," and "Seniors."</p>
<p>After that, I converted the "Tenure" in months to "Tenure in Years" by dividing by 12 and filled the values in a new column called "Tenure (Year)."</p>
<p>Finally, I categoriezed "Payment Dealy" column to Long Delay and Short Delay in filled the values in a new column called "Payment Delay Categories".</p>

### Changing the Data Type
<p>I changed the data type of the "Total Spend" column from General to Dollar Currency.</p>

## Define Metrics for Dashboard
<p>We create the following pivot tables to answer our business questions.</p>

### Metric 1: Lifetime Value of Churned and Non-Churned Customers
<b>Values:</b> CustomerID (By Count), Total Spend (By Sum), Tenure_Year (Average) <br>
<b>Rows:</b> Churn<br>
<b>Columns:</b> Values<br>

#### Calculating LTV for Churned Customer
<p>First, we need to calculate the "Average Revenue per Churned Customer." To do this, we divide the total spend by the number of churned customers from the pivot table above. Next, we multiply this result by the average tenure of churned customers from the same table. This will give us the LTV for churned customers.</p>

#### Calculating LTV for Non-Churned Customer
<p>First, we need to calculate the "Average Revenue per Non-Churned Customer." To do this, we divide the total spend by the number of non-churned customers from the pivot table above. Next, we multiply this result by the average tenure of non-churned customers from the same table. This will give us the LTV for non-churned customers.</p>

### Metric 2: Churn Rate by Subscription Type
<b>Values:</b> Churn Rate (By Sum) <br>
<b>Rows:</b> Subscription Type<br>

### Metric 3: Number of Churns by Contract Length
<b>Values:</b> Churn (By Sum)<br>
<b>Rows:</b> Contract Length

### Metric 4: Churn Rate by Payment Delay
<b>Values:</b> Churn Rate (By Sum)<br>
<b>Rows:</b> Payment Delay Category<br>

### Metric 5: Number of Churns by Age Group and Gender
<b>Values:</b> Churn (By Sum)<br>
<b>Rows:</b> Age Category<br>
<b>Columns:</b> Gender<br>

### Metric 6: Number of Churns by Tenure (Year)
<b>Values:</b> Churn (By Sum)<br>
<b>Rows:</b> Tenure<br>

## Creating Charts for Certain Metrics

### For Metric 2, Churn Rate by Subscription Type
<p>I created <b>Doughnut Chart</b>, for three Subscription Type.</p>
<img width="417" alt="Screenshot 2024-08-01 at 8 21 46 PM" src="https://github.com/user-attachments/assets/4f2867d7-24f9-4bb0-9bd6-ae15dbb3d3c7">

### For Metric 3, Number of Churns by Contract Length
<p>I created <b>Bar Chart</b>, as Contract Length in x-axis and Number of Churns in y-axis.</p>
<img width="480" alt="Screenshot 2024-08-01 at 8 28 23 PM" src="https://github.com/user-attachments/assets/bc5174b5-ef8f-48c2-bf98-02878e7737c6">

### For Metric 4: Churn Rate by Payment Delay
<p>I created <b>Pie Chart</b>, for two types of Payment Delay. </p>
<img width="417" alt="Screenshot 2024-08-01 at 8 22 02 PM" src="https://github.com/user-attachments/assets/642e2c6a-ea44-4233-8d60-428677aa4c82">

### For Metric 5, Number of Churns by Age Group and Gender
<p>I again created <b>Line Chart</b>, as Age Group in x-axis and Number of Churns in y-axis.</p>
<img width="480" alt="Screenshot 2024-08-01 at 8 29 34 PM" src="https://github.com/user-attachments/assets/db6c1033-871c-4311-a59e-0200f08ae102">

### For Metric 6, Number of Churns by Tenure (Year)
<p>I created <b>Line Chart</b>, as Tenure (Year) in x-axis and Number of Churns in y-axis.</p>
<img width="480" alt="Screenshot 2024-08-01 at 8 30 39 PM" src="https://github.com/user-attachments/assets/ac97246e-dcef-4a2b-8424-9bad39c500f3">


### Creating Slicer
<p>I created a slicer to manipulate the data shown in charts. By using these tools, we can gain different insights through filtering.</p>

## Dashboard
<img width="1403" alt="Screenshot 2024-08-01 at 8 31 56 PM" src="https://github.com/user-attachments/assets/bdb0d1e6-104b-4d16-bd04-694d4f8b2d98">



## Analysis From Dashboard

<p>By analyzing the dashboard, we can get an overview of the sales performance across different products, categories, and states. Observing these performances allows us to provide recommendations that will improve overall sales for the e-commerce website.</p>

### Analysis 1: Need to Restock Inventory Between March and May and in September
<p>Sales across all product categories tend to increase between March and May, and again in September. It's important to ensure inventory levels are sufficient during these peak periods to meet the higher demand.</p>

### Analysis 2: Increase Marketing Efforts in July and August
<p>Sales across all product categories tend to decrease in July and August. We need to run more marketing campaigns during these months, especially for the top-selling products: monitors, CPUs, and graphics cards.</p>

### Analysis 3: Lowest and Highest Sales States
<p>The chart shows that Andaman and Nicobar Islands have the lowest sales, while Maharashtra has the highest. Most states have consistent sales, with Gujarat and Uttar Pradesh having the second-highest sales. We should consider conducting surveys to analyze the reasons for low sales in Andaman and Nicobar Islands. For high-performing states, ensure sufficient stock to meet the high demand.</p>



