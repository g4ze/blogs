---
title: "Unveiling The Tier-3 DBMS-101"
seoTitle: "Tier-3 Database Management Systems (DBMS)"
seoDescription: "Handling the Data Mines: powering big data"
datePublished: Sun Jun 11 2023 18:09:34 GMT+0000 (Coordinated Universal Time)
cuid: clirqpi8w000709l93pbtbb5x
slug: dbms-101
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1686506962717/dbca05c6-b169-4225-98f3-2a66c8c129fb.webp
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1686506588293/97e1cb14-00cc-47f5-a9e7-7837cadc5542.webp
tags: big-data, ecommerce, architecture, dbms, 3-tier-architecture

---

## What?!

In the realm of database management systems (DBMS), the three-tier client-server architecture stands tall as a robust framework. <mark>With the goal of separating</mark> user applications and physical databases, this architecture unleashes its potential in diverse domains, including the bustling world of e-commerce. In this blog post, we will explore the key components of a tier-3 DBMS, provide a high-level overview, and shed light on how it efficiently handles data reading and writing for large-scale applications.

## The Three Levels

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686506356057/f443f074-6d92-4030-a67b-149c4214f699.png align="center")

1. ### User Interface:
    
    The User Interface (UI) acts as the bridge between users and the DBMS. It provides an intuitive and user-friendly interface for interacting with the system. From inputting queries and fetching results to managing preferences and generating reports, the UI facilitates seamless user interactions.
    
2. ### Application Logic Layer:
    
    The Application Logic Layer serves as the brain of the DBMS. It handles the core functionalities, including query parsing, query optimization, and query execution. Here, the DBMS takes user queries, optimizes them to ensure efficient data retrieval, and orchestrates the execution of these queries using the Execution Engine. The Data Access Layer facilitates interaction with the Data Storage Layer.
    
3. ### Data Storage Layer:
    
    At the heart of the tier 3 architecture lies the Data Storage Layer. This layer manages the physical databases and metadata repository. It handles tasks such as data storage, retrieval, indexing, and organization. The DBMS ensures data integrity and consistency through concurrency control mechanisms, transaction management, and backup and recovery strategies.
    

## Handling Data Reading and Writing

A single byte of memory can be accessed by only one instance at a time and this poses a new threat to our scalability factor. Now, let's explore how a tier 3 architecture gracefully handles data reading and writing for large-scale applications:

1. ### Lock Granularity:
    
    To balance concurrency and data consistency, tier 3 DBMS utilizes fine-grained locks. These locks allow multiple users to read the data simultaneously, preventing conflicts. Write operations are synchronized to maintain data integrity, ensuring that only one user can modify the data at a given time.
    
2. ### Hardware and Scalability:
    
    To cater to the demands of huge applications, tier 3 DBMS leverages powerful hardware resources. High-speed storage, ample memory, and efficient processing power enable seamless data access and quick query execution. Scaling the infrastructure horizontally ensures optimal performance by distributing the workload across multiple nodes.
    
3. ### Reducing Network Latency:
    
    Tier 3 DBMS tackles the challenge of network latency by strategically placing replicas of the data closer to the users. Employing techniques like data replication and caching, minimizes the distance between users and the data, resulting in faster access and improved user experience.
    

A world where <mark>data is the king</mark>, the tier 3 DBMS architecture reigns supreme. With its clear separation of layers, efficient data reading and writing mechanisms, fine-grained locks, optimized hardware utilization, and reduced network latency, it paves the way for scalable and high-performance systems. Whether you're browsing products, placing orders, or managing inventory, tier 3 DBMS ensures a seamless experience, empowering <mark>businesses to thrive in the digital realm</mark>.