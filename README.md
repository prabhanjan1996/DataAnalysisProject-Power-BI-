# DataAnalysisProject-Power-BI

------->  Sales Insights Data Analysis Project

------->SQL database dump is in db_dump.sql file above.

-------------------------------------------------------------------------------------------------------------
Data Analysis Using SQL
-------------------------------------------------------------------------------------------------------------

1) Show all customer records

SELECT * FROM customers;

2) Show total number of customers

SELECT count(*) FROM customers;

3) Show transactions for Chennai market (market code for chennai is Mark001

SELECT * FROM transactions where market_code='Mark001';

4) Show distrinct product codes that were sold in chennai

SELECT distinct product_code FROM transactions where market_code='Mark001';

5) Show transactions where currency is US dollars

SELECT * from transactions where currency="USD"

6) Show transactions in 2020 join by date table

SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;

7) Show total revenue in year 2020,

SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";

8) Show total revenue in year 2020, January Month,

SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");

9) Show total revenue in year 2020 in Chennai

SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.market_code="Mark001";

      Data Analysis Using Power BI
      ----------------------------
(#)Formula to create norm_amount column

= Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] ="USD#(cr)" then [sales_amount]*75 else [sales_amount], 

------------------------------------------------------------


Other more Queries question
===========================

To increase the sales growth , Sales director need to look into these areas.
--> Revenue by Zone

--> Sales Quantity by Zone 

--> Revenue Trend

--> Revenue by Markets (units should be in Thousands)

--> Sales Quantity by Markets

--> Top 5 Customers by Revenue

--> Top 5 Products by Revenue

--> Last 5 years Revenue (overall sales)

--> Last 5 years Revenue by Zone. (We can focus to increase sales on particular zone by increasing sales employees , promoting\advertising products)

--> Identify Less Revenue getting from Customers (get the feedback from them, attract offers & discounts)

--> Identify Top Revenue getting from Customers ( increase products which have more price)

--> Identify the markets which sales is very very less ( stop sales in those areas to avoid transport charges and  sales employees, this amount can be invest on other areas )

--> Display the return products Quantity from Zone & Customer .

--> Identify which products increasing more Revenue from Zone, Market , customer (main objective is to increase sales growth)

--> Identify on which month sales growth is increasing by checking with previous years(so that company can be ready with quantity to increase the products distribution)

--> Few records sales amount can be zero by giving offer\discount when they purchased other huge products. So we need to maintain those products quantity.

--> Inventory within a monthly time frame versus a yearly time frame can have a huge impact on the effectiveness of a supply chain.
