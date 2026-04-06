# Instagram Thrift Creator Store – ER Diagram

The database design models how a small creator store manages products, customers, orders, payments, and shipping. The system supports both thrifted products (unique pieces) and handmade products (multiple units).

## Overview

This project contains the **Entity Relationship Diagram (ERD)** for a small Instagram-based store that sells **thrifted fashion items** and **handmade products**. The database design helps the business manage products, customers, orders, payments, and shipping information.

The goal of this design is to support the workflow of a small online store that initially receives orders through **Instagram DMs and WhatsApp**.

---

## Entities Included

### Customers

Stores customer information such as:

* username
* email
* phone
* address details

### Products

Stores product details including:

* product type (thrifted or handmade)
* category (men, women, child)
* size
* color
* condition
* price
* stock quantity

### Orders

Represents orders placed by customers.

### Order Items

A **junction table** that connects orders and products, allowing one order to contain multiple products.

### Payments

Stores payment information such as:

* payment method
* payment status
* transaction id
* payment date

### Shipping

Tracks delivery information including:

* shipping status
* shipping address
* tracking number
* shipped and delivered dates

### Thrifted Products

Stores additional information specific to thrifted items, such as:

* original brand
* purchase source

---

## Relationships

* A **customer can place multiple orders**.
* An **order can contain multiple products**.
* Products and orders are connected through the **order_items** table.
* Each order can have **payment details**.
* Each order can have **shipping information**.
* If a product is thrifted, it may have additional data in the **thrifted_products** table.

---

## Files in This Repository

* `er-diagram.png` – Exported image of the ER diagram
* `README.md` – Project documentation

---

## Purpose

This ER diagram demonstrates how a database can be designed to manage an online thrift and handmade product store efficiently.

---

## Author

Sudhanshu Mundhe
