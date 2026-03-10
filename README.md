README
Customer Behavior Analysis using Big Data Technologies
Project Overview
This project analyzes customer behavior in an e-commerce environment using multiple database technologies and big data tools.

The goal is to integrate several datasets and analyze relationships between customers, products, and orders.

Technologies Used
Apache Spark (Databricks)
Spark SQL
JSON document data
Neo4j Graph Database
Data Sources
The following datasets were used:

customers.csv – customer information
orders.csv – purchase transactions
events.csv – customer interaction events
FashionDataset.csv – product catalog
These datasets simulate an online retail platform.

Data Processing
Apache Spark was used to:

load multiple datasets
clean and transform the data
integrate the datasets using Spark SQL
Customer event data was also converted into JSON format to simulate document database storage.

Graph Database
A Neo4j graph database was used to analyze relationships between entities.

Nodes
Customer
Order
Products
Relationships
PLACED – customer places an order
CONTAINS – order contains products
INTERACTED_WITH – customer interacts with products
Analysis
Graph Database Analysis (Neo4j)
Neo4j was used to analyze relationships between customers, orders, and products.

Graph model:

Customer → PLACED → Order → CONTAINS → Product

Example Cypher queries:

Top purchased products:

MATCH (o:Order)-[:CONTAINS]->(p:Products) RETURN p.BrandName, count(o) AS purchases ORDER BY purchases DESC LIMIT 10;

Customer purchase relationships:

MATCH (c:Customer)-[:PLACED]->(o:Order)-[:CONTAINS]->(p:Products) RETURN c,o,p LIMIT 20;

Example analyses performed:

identifying the most popular products
analyzing customer purchasing patterns
finding products frequently purchased together
Conclusion
This project demonstrates how Apache Spark can be used for big data integration and processing, while a graph database can be used to analyze relationships between entities in an e-commerce system.

# Customer Behavior Analysis using Big Data Technologies

## Project Overview

This project analyzes customer behavior in an e-commerce environment using multiple database technologies and big data tools.

The goal of the project is to integrate several datasets and analyze relationships between customers, products, and orders.  
The analysis is performed using Apache Spark for data processing and Neo4j for graph-based relationship analysis.

---

## Technologies Used

- Apache Spark (Databricks)
- Spark SQL
- JSON document data
- Neo4j Graph Database

---

## Data Sources

The following datasets were used:

- **customers.csv** – customer information
- **orders.csv** – purchase transactions
- **events.csv** – customer interaction events
- **FashionDataset.csv** – product catalog

These datasets simulate an online retail platform where customers interact with products and place orders.

---

## Data Processing

Apache Spark was used to:

- load multiple datasets
- clean and transform the data
- integrate the datasets using Spark SQL

Customer event data was also converted into **JSON format** to simulate document database storage and demonstrate the use of semi-structured data.

---

## Graph Database (Neo4j)

A Neo4j graph database was used to analyze relationships between customers, orders, and products.

### Nodes

- Customer
- Order
- Products

### Relationships

- **PLACED** – customer places an order
- **CONTAINS** – order contains products
- **INTERACTED_WITH** – customer interacts with products

### Graph Model

Customer → PLACED → Order → CONTAINS → Product

---

## Example Cypher Queries

### Top Purchased Products

```cypher
MATCH (o:Order)-[:CONTAINS]->(p:Products)
RETURN p.BrandName, count(o) AS purchases
ORDER BY purchases DESC
LIMIT 10;

Customer Purchase Relationships
MATCH (c:Customer)-[:PLACED]->(o:Order)-[:CONTAINS]->(p:Products)
RETURN c,o,p
LIMIT 20;
