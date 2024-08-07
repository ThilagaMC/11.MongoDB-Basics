# 11.MongoDB-Basics

#Note:
Products is my db items is collections from my code.

# MongoDB Operations Documentation

This document provides an overview of various MongoDB queries and operations performed on the `items` collection. 

## Queries and Operations

### 1. Find All Information About Each Product

To retrieve all fields and details for each product in the `items` collection:
```shell
db.items.find()
```

### 2. Find Products with Prices Between 400 and 800

To find products with a `product_price` between 400 and 800 (inclusive):
```shell
db.items.find({ product_price: { $gte: 400, $lte: 800 } })
```

### 3. Find Products with Prices Not Between 400 and 600

To find products where `product_price` is not between 400 and 600:
```shell
db.items.find({ product_price: { $not: { $gte: 400, $lte: 600 } } })
```

### 4. List Four Products with Prices Greater Than 500

To list up to four products where the `product_price` is greater than 500:
```shell
db.items.find({ product_price: { $gt: 500 } }).limit(4)
```

### 5. Find Product Name and Product Material of Each Product

To retrieve only the `product_name` and `product_material` fields for each product:
```shell
db.items.find({}, { product_name: 1, product_material: 1, _id: 0 })
```

### 6. Find Product with ID of 10

To find the product with an `id` of "10":
```shell
db.items.find({ id: "10" })
```

### 7. Find Only Product Name and Product Material

To retrieve only the `product_name` and `product_material` fields for all products:
```shell
db.items.find({}, { product_name: 1, product_material: 1, _id: 0 })
```

### 8. Find All Products with "Soft" in Product Material

To find all products where `product_material` contains the substring "Soft":
```shell
db.items.find({ product_material: { $regex: "Soft", $options: "i" } })
```

### 9. Find Products with Product Color Indigo and Price 492.00

To find products with a `product_color` of "indigo" and `product_price` of 492.00:
```shell
db.items.find({ product_color: "indigo", product_price: 492.00 })
```

### 10. Delete Products with Price Value of 28

To delete all products where `product_price` is 28.00:
```shell
db.items.deleteMany({ product_price: 28.00 })
```