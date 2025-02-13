# Sales Insights Data Analysis
This project analyzes sales data for a hardware company, providing insights into revenue, market performance, and product trends. The analysis is based on a MySQL database containing transaction data, customer information, product details, and market data.
# Dashboard
![Image](https://github.com/user-attachments/assets/268e516d-3095-4b28-84a9-c5531289efd4)
![Image](https://github.com/user-attachments/assets/c9cf1367-d889-411c-91b9-6521ed2524a1)
# Features
- Data analysis using MySQL
- Visualization of key performance indicators
- Market and product performance evaluation
- Customer segmentation analysis
# Database Structure
- 'customers': Customer information
- 'date': Date dimension table
- 'markets': Market and zone information
- 'products': Product details
- 'transactions': Sales transaction data

# Usage
- Set up the MySQL database using the provided SQL dump file.
- Run SQL queries to extract insights from the data.
- Use visualization tools to create dashboards and reports.

### Data Analysis Using SQL

1. Show all customer records

    `SELECT * FROM customers;`

1. Show total number of customers

    `SELECT count(*) FROM customers;`

1. Show transactions for Chennai market (market code for chennai is Mark001

    `SELECT * FROM transactions where market_code='Mark001';`

1. Show distrinct product codes that were sold in chennai

    `SELECT distinct product_code FROM transactions where market_code='Mark001';`

1. Show transactions where currency is US dollars

    `SELECT * from transactions where currency="USD"`

1. Show transactions in 2020 join by date table

    `SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;`

1. Show total revenue in year 2020,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";`
	
1. Show total revenue in year 2020, January Month,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`

1. Show total revenue in year 2020 in Chennai

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020
and transactions.market_code="Mark001";`




