# Simple E-Commerce Database Schema

## Overview

This repository contains the schema for a simple e-commerce application. It includes the structure for categories, products, customers, employees, departments, orders, order items, and product bundles. This schema is designed to efficiently manage product listings, customer accounts, orders, employee data, and promotional bundles for an e-commerce platform.

---

## Features

- **Product Categories**: Organize products into distinct categories.
- **Customer Management**: Store and manage customer information securely.
- **Order Processing**: Track orders and their details.
- **Product Bundles**: Create and manage promotional product bundles.
- **Employee and Department Management**: Maintain records of employees and their respective departments.

---

## Database Schema

The schema defines the following tables:

1. **Category**
   - Holds product categories for the e-commerce store.
   - Attributes: `id`, `name`, `created_at`, `updated_at`

2. **Product**
   - Stores details of products available for purchase.
   - Attributes: `id`, `category_id`, `name`, `description`, `price`, `stock_quantity`, `created_at`, `updated_at`

3. **Customer**
   - Stores customer information.
   - Attributes: `id`, `firstname`, `lastname`, `email`, `password`, `created_at`, `updated_at`

4. **Order**
   - Tracks customer orders.
   - Attributes: `id`, `customer_id`, `order_date`, `total_amount`, `created_at`, `updated_at`

5. **Order Items**
   - Stores details of products ordered within each order.
   - Attributes: `id`, `order_id`, `product_id`, `quantity`, `unit_price`, `created_at`, `updated_at`

6. **Product Bundle**
   - Defines promotional bundles of products.
   - Attributes: `id`, `name`, `description`, `discount_percentage`, `created_at`, `updated_at`

7. **Product Bundle Items**
   - Links products to their respective bundles.
   - Attributes: `id`, `bundle_id`, `product_id`, `quantity`

8. **Employee**
   - Stores employee information.
   - Attributes: `id`, `firstname`, `lastname`, `email`, `password`, `role`, `phone`, `department_id`, `created_at`, `updated_at`

9. **Department**
   - Defines departments within the organization.
   - Attributes: `id`, `name`, `created_at`, `updated_at`

---

## Entity-Relationship Diagram (ERD)

The ERD visualizes the relationships between entities in the database. It includes:

- **Category**: One-to-Many with Product
- **Product**: Many-to-One with Category, Many-to-Many with Product Bundle through Product Bundle Items, One-to-Many with Order Items
- **Customer**: One-to-Many with Order
- **Order**: Many-to-One with Customer, One-to-Many with Order Items
- **Order Items**: Many-to-One with Order and Product
- **Product Bundle**: One-to-Many with Product Bundle Items
- **Product Bundle Items**: Many-to-One with Product Bundle and Product
- **Employee**: Many-to-One with Department
- **Department**: One-to-Many with Employee

## ERD (Entity-Relationship Diagram)

The ERD for this schema can be viewed below:

![ERD Diagram](./images/DBs-eCommerce.drawio.png)

or

You can view the ERD diagram
[here](https://viewer.diagrams.net/?tags=%7B%7D&lightbox=1&highlight=0000FF&layers=1&nav=1&title=DBs-eCommerce.drawio&dark=auto#R%3Cmxfile%3E%3Cdiagram%20name%3D%22Page-1%22%20id%3D%22gt_yiPwK9PLadmMUtM0C%22%3E7Vxbc6M2FP41nmkfkuFu8ri57LbTbDez6XTbp4wMsq0GECvkdby%2FvhJIgLAw2LEdkjgvRkf3c%2FuODiIj%2Byp%2B%2BkRAOv%2BMQxiNLCN8GtnXI8syDddgP5yyKiiuLQgzgkLRqCLco59Q9hTUBQphpjSkGEcUpSoxwEkCA6rQACF4qTab4kidNQUzuEa4D0C0Tv2GQjovqL7cFqf%2FBtFsLmc2DVETA9lYELI5CPGyRrJvRvYVwZgWT%2FHTFYw48yRfin4fW2rLhRGY0D4d0nGK%2Fkz%2B%2FnIbfDbpJ%2FTn5PrjtzMxyg8QLcSGR5YXsfEup5gNy1ZNV4IV3vcFlhVnWS6oD6yB5aRM2JdVPXua8d8rQOEMk5UckK2sGLOoFkwph7eyJYojkLDSZTBHUXgLVnjBd5ZREDzK0uUcE%2FSTjQMiVmUyAqsmVCgOE0u9xT3vycicSvAiCWEoOvGViD6mI8tiLcWgBD%2BWErd4f8j3fCfZbZSkW5BR2UuKmNeGIJvn8%2FECiNAsYc8B6w0JJ5BAzM%2BnX84RhfcpCDhhySyJb4PGcotTFEVXOMIk55Q9nU6tIChXWasJvYnneiV368ohJQ0JhU81klCWTxDHkHJpGaLWEXq7UovLygpMX9DmNQuwpQEAYXmzcuRysq%2FMUkEyY9wuZ%2FPV2Uozqk2nm81tTAYixt6Ead4lF3dWNwj2UNtmRcrNZAuTsZ5tMqbXYjJsXsv45e6PXxkBxFwJkkmWFg30NlSQQ%2FSjScpSkGjXMmEmMcuN4SwoFIcvCSWIIm5SmlXtbXsJiOGWO2PkYidrZM2eNaRnr%2FkA%2FAwIZAoaPgC%2Bso6N7leMbZxvYXGLQPpxfogKuEjDkvP7ULsGgkknH8EpXfPOCc6hre7KBYnNFKBkdpv3ui7RSKCTz8rcaSMWk3wQE1CcSvgBk3z2AuEooLUy8%2F4SmGpYso5s61ixMVToBpCV6pu7EGPNidcRQ%2FHe27pqu9VV16V7R3C4CGir7AcSp1j2a4tTQhf6oaOLU3xrYnt7ilNsqzNQsYz3GKh4hwtUOp18%2FckIIpBlSvU8%2Bi9j3j%2BOYe5728OgEh8npMNHF8GF0YZyVf9AnEseimk%2BdkxzmC2yM21AUEoRTrbZ5GEXlRIUwG2Wk1EcPD58X4CEIrrS9mwGOx3CURC6X6D4rkDY7u0d20FY6w0PB8Kuxg01ZAbDGZSoBnNd%2BgojwI3jpqpRBGKp%2FIRJ%2BIEne1jx5utPSPBf%2BDNIVhJ1m3VfcpFXSMsFBZ8Q%2FUcOx57%2F5fRzV5Sun2rNrleykDAG8U5nxrlhmJJSdDUNSxKq3nlJ6X4HCWKM5mCbE1XVsDdhZIYXJIDdR1XGghnsoVVcDBt1qh7J6ZSoJJJcfD%2FUHNoGnL3DKEckodLWhQqyJabLIYqdi171nFdjILsxkNkcqGDN2kD7guBxRwDa5qIf4WqJSbjuor%2BQEJJWcDB%2BpzDOThHr7pk1P4D6zNrEd52cB3uIWL1Tak1vLv67ili5GhVHz2Yo2hEkYe4EXjR8XSSIPmwdLh52TVUYunHyU2h6oNB03NsNDiY%2FZLY7nOfgc3ZKJb1OYLabwGyfkFlYysV7g%2BZgkVHGtjWc7YXNHCleAJYp8%2FDRA4iZGrSns08weNjXJH5vrzMYHJQpmZp1Xwn1P2HWM65pQK%2Flmsb4YmLs6zDpqiDi%2BSfMElrd%2FvrvLWLWFJGMtlyx6PDpbHm0en9yVMiCMUDRcA6RKWsuIvsTer4AepZI9JrQ09H4GaO8VWBcMgeXe9BTdvaZ9wkA9KdaQPUCH06m%2BwFUUwU4XwNw1linYG8eT3Vv8t4unk5ys60f%2F7aF1Zbs7lHxdeus6Eb%2BvGdkcno7kg2v3nWOwzwcMumuAGmQqanIJ4QaNELZ4wZE6a68me%2FyyNf%2Bwv0tQtRup73m3bPjX35DWcBTlA8pJNzs%2BCdYp%2FPWy6Ca19v5bEA1na854HlL9y6iIbXB3igb9b9PZo%2BU%2B2S%2B%2F%2BL3yeRboM4LZSIHPpgLZa7FGVr9mQqgOa6jDtj3epnnbBrWNhsWcODLZvZ6Fv%2FAdsFc3Q5mIZXcUPXbcrvUe4cbmvvUfu%2FVKr9zbtoX1Z%2BipZbjnbs7q78%2BMDyWwusSb0MEAqnx5rmRf21c03p3vItTl6ZgjPpCy16vFds9LUHixWBMwWsk98bjhsb2Vf1xYyCvOVCL6jN1Aatas5Q3yNoX7Dc%2BbvI8Y%2BO6XCkb2d5W2rOHYgX7tcOjX%2FHfADz1qn7AM94NeKzjIY%2FMvHYanDcwezNtVX0dzz93WKBkOY7pGJ61I%2FA0EhLjiyPjji6tNuBAy9xR3xV0Ed2Oo%2B%2FjnvouFWgwCu80cOFi1y9X3OZrqL19ucKK1T%2BdKZpX%2F7rHvvkf%3C%2Fdiagram%3E%3C%2Fmxfile%3E)

---

## How to Use

1. **Set Up the Database**
   - Run the SQL scripts to create the database and tables.

2. **Insert Dummy Data**
   - Use the provided scripts to populate tables with sample data for testing.

3. **Run Queries**
   - Use the provided SQL queries for generating reports such as daily revenue, top-selling products, and customer orders exceeding a specific amount.

4. **Integrate with Application**
   - Use this schema as a backend database for your e-commerce application.

---

## SQL Queries

### Daily Revenue Report

```sql
SELECT
    COUNT(id) AS orders,
    SUM(o.total_amount) AS revenue
FROM
    "order" o
WHERE
    o.order_date BETWEEN '2024-01-01 00:00:00' AND '2024-01-01 23:59:59';
```

### Monthly Top-Selling Products

```sql
SELECT
    od.product_id,
    p."name",
    COUNT(od.product_id) AS total
FROM
    order_items od
INNER JOIN "order" o ON
    o.id = od.order_id
INNER JOIN product p ON
    od.product_id = p.id
WHERE
    DATE_TRUNC('month', o.order_date) = '2024-01-01'::DATE
GROUP BY
    od.product_id, p."name"
ORDER BY
    total DESC
LIMIT 10;
```

### Customers with Orders Over $500

```sql
SELECT
    c.id AS customer_id,
    (c.firstname || ' ' || c.lastname) AS fullname,
    SUM(o.total_amount) AS total_amount
FROM
    "order" o
INNER JOIN customer c ON
    o.customer_id = c.id
WHERE
    o.total_amount > 500
    AND order_date >= DATE_TRUNC('month', CURRENT_DATE) - INTERVAL '1 month'
    AND order_date < DATE_TRUNC('month', CURRENT_DATE)
GROUP BY
    c.id
ORDER BY
    total_amount DESC;
```

---

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request with your changes.

---

## License

This project is licensed under the MIT License.
