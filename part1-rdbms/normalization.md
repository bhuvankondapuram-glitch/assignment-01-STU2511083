## Anomaly Analysis
1.Insert Anomaly  
In the dataset, product details are stored along with order details. This means a new product cannot be added unless there is an order associated with it.  
Example: A new product cannot be inserted without creating a fake order_id.

2.Update Anomaly  
Customer details such as customer_name and customer_city are repeated across multiple rows. If a customer’s city changes, all rows must be updated. Missing even one row will lead to inconsistent data.  
Example: Same customer_id appears multiple times.

3.Delete Anomaly  
If an order is deleted, all information related to that product or customer in that row may also be lost.  
Example: Deleting the only record of a product removes all its details.
