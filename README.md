# MONGO-DB# MongoDB – Notes for GitHub Repository

## Introduction

**MongoDB** is a **NoSQL (Not Only SQL)** database that stores data in **JSON-like documents** called **BSON (Binary JSON)**. Unlike traditional relational databases that use tables and rows, MongoDB stores data in collections and documents, making it flexible, scalable, and easy to work with modern applications.

---

# Features of MongoDB

* Document-oriented database
* Schema-less (Flexible structure)
* High performance
* Easy horizontal scaling
* Supports indexing for faster searches
* Replication for high availability
* Aggregation framework for data analysis
* Cross-platform support
* Open-source with a large community

---

# Why Use MongoDB?

* Handles large amounts of data efficiently.
* Easy to modify data structure without changing the entire database.
* Suitable for cloud-based applications.
* Faster development due to flexible schema.
* Excellent support for real-time applications.

---

# MongoDB Architecture

```
Database
   │
   ├── Collection
   │      │
   │      ├── Document
   │      ├── Document
   │      └── Document
```

### Database

A container that holds multiple collections.

### Collection

A group of related documents (similar to a table in SQL).

### Document

A single record stored in JSON/BSON format.

Example:

```json
{
  "name": "Ganesh",
  "age": 20,
  "course": "Computer Science",
  "skills": ["Python", "Java", "MongoDB"]
}
```

---

# SQL vs MongoDB

| SQL Database | MongoDB                         |
| ------------ | ------------------------------- |
| Database     | Database                        |
| Table        | Collection                      |
| Row          | Document                        |
| Column       | Field                           |
| Primary Key  | _id                             |
| Fixed Schema | Flexible Schema                 |
| Joins        | Embedded Documents / References |

---

# Advantages

* Flexible data model
* High scalability
* Fast read/write operations
* Easy integration with web applications
* Supports large datasets
* Built-in replication
* Automatic sharding
* Rich querying capabilities

---

# Disadvantages

* More memory usage compared to some SQL databases
* Complex joins are limited
* Transactions may be slower than relational databases for highly structured data
* Data duplication can occur due to embedded documents

---

# Installation Steps

1. Download MongoDB Community Server.
2. Install MongoDB.
3. Install MongoDB Shell (mongosh).
4. Add MongoDB to the system PATH.
5. Start the MongoDB service.
6. Open Command Prompt or Terminal.
7. Run:

```bash
mongosh
```

If connected successfully, MongoDB is ready to use.

---

# Basic MongoDB Commands

## Show Databases

```javascript
show dbs
```

## Create or Switch Database

```javascript
use CollegeDB
```

## Show Current Database

```javascript
db
```

## Create Collection

```javascript
db.createCollection("students")
```

## Show Collections

```javascript
show collections
```

---

# CRUD Operations

## Insert One Document

```javascript
db.students.insertOne({
  name: "Ganesh",
  age: 20,
  branch: "CSE"
})
```

---

## Insert Multiple Documents

```javascript
db.students.insertMany([
  {name:"Rahul", age:21},
  {name:"Priya", age:22},
  {name:"Amit", age:20}
])
```

---

## Read All Documents

```javascript
db.students.find()
```

---

## Read Specific Document

```javascript
db.students.find({name:"Ganesh"})
```

---

## Update One Document

```javascript
db.students.updateOne(
  {name:"Ganesh"},
  {$set:{age:21}}
)
```

---

## Update Multiple Documents

```javascript
db.students.updateMany(
  {},
  {$set:{college:"ABC College"}}
)
```

---

## Delete One Document

```javascript
db.students.deleteOne({name:"Ganesh"})
```

---

## Delete Multiple Documents

```javascript
db.students.deleteMany({age:20})
```

---

# Useful Query Operators

### Greater Than

```javascript
db.students.find({age:{$gt:20}})
```

### Less Than

```javascript
db.students.find({age:{$lt:22}})
```

### Equal To

```javascript
db.students.find({age:21})
```

### Not Equal

```javascript
db.students.find({age:{$ne:20}})
```

### AND

```javascript
db.students.find({
  age:21,
  branch:"CSE"
})
```

### OR

```javascript
db.students.find({
  $or:[
    {branch:"CSE"},
    {branch:"ISE"}
  ]
})
```

---

# Sorting

Ascending

```javascript
db.students.find().sort({age:1})
```

Descending

```javascript
db.students.find().sort({age:-1})
```

---

# Limit Results

```javascript
db.students.find().limit(5)
```

---

# Count Documents

```javascript
db.students.countDocuments()
```

---

# Index Example

Create Index

```javascript
db.students.createIndex({name:1})
```

View Indexes

```javascript
db.students.getIndexes()
```

---

# MongoDB Data Types

* String
* Integer
* Double
* Boolean
* Array
* Object
* Null
* Date
* ObjectId
* Binary Data

---

# Real-World Applications

* E-commerce websites
* Social media platforms
* Content management systems
* Chat applications
* Banking analytics
* Gaming applications
* IoT systems
* Online education platforms

---

# MongoDB with Python

Install Driver

```bash
pip install pymongo
```

Example

```python
from pymongo import MongoClient

client = MongoClient("mongodb://localhost:27017/")

db = client["CollegeDB"]

students = db["students"]

students.insert_one({
    "name": "Ganesh",
    "age": 20,
    "course": "CSE"
})

print("Data inserted successfully!")
```

---

# Best Practices

* Design collections based on application needs.
* Create indexes only where required.
* Use embedded documents when appropriate.
* Validate data before insertion.
* Perform regular database backups.
* Secure the database with authentication and authorization.
* Monitor database performance and optimize queries.

---

# Summary

MongoDB is a powerful NoSQL database that stores data as flexible documents instead of tables. It is widely used for modern web, mobile, cloud, and enterprise applications because of its scalability, high performance, and ease of development. MongoDB is an excellent choice for applications with rapidly changing data structures and large volumes of data.

---

# Learning Outcomes

After studying MongoDB, you should be able to:

* Understand NoSQL database concepts.
* Create and manage databases and collections.
* Perform CRUD operations.
* Use query operators and sorting.
* Create indexes for better performance.
* Connect MongoDB with Python applications.
* Design scalable database solutions for real-world projects.
