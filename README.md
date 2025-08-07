# DATA-ANALYSIS-TASK2

CODTECH IT SOLUTIONS PVT.LTD

Dhana Packiyam M

CT04DH2476

SQL

4 weeks

Neela Santhosh Kumar

Advanced Data Analysis Using SQL: Description
This task focuses on using advanced SQL techniques — specifically window functions, subqueries, and common table expressions (CTEs) — to generate a meaningful data analysis report. The dataset consists of two relational tables: Customers and Orders. The goal is to extract trends and patterns from customer order data, such as identifying top customers, ranking product demand, analyzing order behavior, and detecting data quality issues.

🔹 1. Using CTEs and Window Functions to Rank Customers by Quantity Ordered
The first analysis used a Common Table Expression (CTE) to calculate the total quantity of items ordered by each customer. After computing the totals, we applied the RANK() window function to rank customers from highest to lowest total quantity. This approach makes the query modular, readable, and easy to extend. It revealed that Bob was the top customer by order quantity, followed by Alice, while others had not made any purchases. This ranking is useful in business scenarios for identifying VIP customers or frequent buyers.

🔹 2. Detecting Orphan Orders with a Subquery
Data quality is critical for reliable analytics. We used a subquery to identify orders made by customers who do not exist in the Customers table. This situation typically arises due to missing or incorrect foreign key references. The query filtered out records in the Orders table where CustomerID did not match any existing CustomerID in the Customers table. We discovered an order (OrderID 104) with CustomerID 5, which had no corresponding entry in the Customers table — indicating a data integrity issue. This is crucial for maintaining accurate reporting and should trigger data cleanup or validation processes.

🔹 3. Tracking Order Sequences Per Customer
To study purchasing behavior, we used the ROW_NUMBER() window function to assign a sequence number to each order per customer, ordered chronologically. This shows how many times each customer has ordered and in what order. It revealed that Bob had placed multiple orders, whereas Alice had only one. This type of insight helps in understanding customer engagement, retention, and buying patterns over time.

🔹 4. Ranking Products by Demand Using CTE + DENSE_RANK()
A separate analysis ranked products by their total quantity ordered. Again, a CTE was used to summarize the total quantity per product. Then, the DENSE_RANK() window function was used to assign a ranking based on demand. This helped identify which products are the most popular or frequently ordered. According to the result, the “Phone” product ranked highest in demand, while other products had lower but equal demand. Such insights are valuable for inventory management, marketing focus, or product prioritization

OUTPUT:

<img width="431" height="793" alt="Image" src="https://github.com/user-attachments/assets/61397fcf-64be-408b-a7d4-d9deaf53e86e" />
