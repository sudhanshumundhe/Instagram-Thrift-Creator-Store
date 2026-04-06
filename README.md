# Instagram Thrift & Handmade Store – ER Diagram

## Overview

This project contains the **Entity Relationship Diagram (ERD)** for a small Instagram-based store that sells **thrifted fashion items** and **handmade products**.
The database is designed to help the store owner manage **customers, products, orders, payments, and shipping details** efficiently.

The system supports both:

* **Thrifted items** (usually unique pieces)
* **Handmade products** (which may have multiple units in stock)

---

## Database Entities

### 1. Customers

Stores customer information and address details.

**Attributes**

* `customer_id` (PK)
* `user_name`
* `email`
* `phone`
* `country`
* `state`
* `city`
* `building_number`

---

### 2. Orders

Represents orders placed by customers.

**Attributes**

* `order_id` (PK)
* `customer_id` (FK)
* `order_date`
* `status`
* `total_amount`

---

### 3. Order Items

Acts as a **junction table** between orders and products.
It allows one order to contain multiple products.

**Attributes**

* `order_item_id` (PK)
* `order_id` (FK)
* `product_id` (FK)
* `quantity`
* `price`

---

### 4. Products

Stores product details for both thrifted and handmade items.

**Attributes**

* `product_id` (PK)
* `thrift_category_id`
* `type` (thrifted / handmade)
* `category` (men / women / child)
* `size`
* `color`
* `condition`
* `price`
* `stock_quantity`
* `created_at`
* `updated_at`

---

### 5. Shipping

Stores shipping and delivery information for orders.

**Attributes**

* `shipping_id` (PK)
* `order_id` (FK)
* `shipping_address`
* `shipping_status`
* `tracking_number`
* `shipped_date`
* `delivered_date`

---

### 6. Payments

Stores payment details related to orders.

**Attributes**

* `payment_id` (PK)
* `order_id` (FK)
* `payment_method`
* `payment_status`
* `amount`
* `transaction_id`
* `payment_date`

---

### 7. Thrifted Products

Stores additional details for thrifted items.

**Attributes**

* `thrifted_id` (PK)
* `product_id` (FK)
* `original_brand`
* `purchase_source`

---

## Relationships

* A **customer can place multiple orders**
* An **order can contain multiple products**
* Orders and products are connected using **order_items**
* Each order has **shipping information**
* Each order has **payment details**
* Some products may have additional data stored in **thrifted_products**

---

## Entity Relationships

* `customers.customer_id < orders.customer_id`
* `orders.order_id < order_items.order_id`
* `products.product_id < order_items.product_id`
* `orders.order_id < shipping.order_id`
* `orders.order_id < payments.order_id`
* `products.product_id < thrifted_products.product_id`

---

## Purpose of the Project

This ER diagram demonstrates how a database can be designed to support a growing Instagram-based thrift and handmade product store.
It ensures efficient **product management, order tracking, payment processing, and shipping management**.

---

## Author

Sudhanshu Mundhe
