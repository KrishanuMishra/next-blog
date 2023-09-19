---
title: "Database Management System - NPTEL"
subtitle: "This is an article enlisting what and how I prepared for my NPTEL - DBMS Exam."
date: "2023-09-19"
---

## Why DBMS?
A Database Management System (DBMS) surpasses file systems due to its robust features.
- Data Integrity
- Access control and encryption.
- Querying and indexing, data retrieval is efficient.
- Concurrent access with locking and transaction mechanisms.
- Minimizes redundancy by normalization, optimizing storage.
- It scales both vertically and horizontally, and performance tuning tools enhance efficiency.
- Built-in backup and recovery System

## Levels of Abstraction

- Physical Abstraction:
    - Describes how data is stored in DB.

- Logical Abstraction:
    - Describes the data store and relationship among data. 

- View Abstraction:
    - Hides details of data types and also for security

## Schema & Instance

*Schema* &rarr; Logical and Physical structure of Database.

*Instance* &rarr; Actual data of the tabel.


|   Name   | CustomerID | AccountNO |  MobileNo   |
|----------|------------|-----------|-------------|
| Krishanu |    123     |   901923  |  9461001212 |
| Pavan Laha | 7628     |   917322  |  9830100291 |


## Data Models

| Language           | Use Case                                                                                                          |
|--------------------|------------------------------------------------------------------------------------------------------------------|
| DDL (Data Definition Language) | Defines and manages the structure of the database.                                                             |
| DML (Data Manipulation Language) | Manipulates and interacts with the data in the database.                                                        |
| DQL (Data Query Language) | Retrieves data from the database.                                                                               |
| DCL (Data Control Language) | Manages access control and permissions for data within the database.                                             |
| TCL (Transaction Control Language) | Manages transactions within the database.                                                                         |
| SQL (Structured Query Language) | Universal language for interacting with relational databases.


```mermaid
bar
  title Sample Bar Chart
  data:
    'Category A' : 5
    'Category B' : 10
    'Category C' : 8
    'Category D' : 15