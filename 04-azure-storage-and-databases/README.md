# Lesson 4: Azure Storage & Databases

## Learning Objectives

Understand the main Azure Storage and Database services, their use cases, and how a Scrum Master can recognize storage-related dependencies and database issues that affect delivery.

## Key Concepts

### 1. What Is Azure Storage?

Azure Storage provides cloud-based services to store, manage, and access different types of data.

Different storage services are designed for different requirements, such as storing files, sharing data, processing messages, and providing storage for virtual machines.

### 2. Azure Blob Storage

Azure Blob Storage is used to store large amounts of unstructured data, such as images, videos, documents, and backups.

**When to use it:**
- An application needs to store images, videos, or PDF documents.
- A team needs cloud storage for application backups.
- An application generates large amounts of unstructured data.

**Key concepts:**
- Storage Account: Top-level Azure storage resource.
- Container: Logical grouping of blobs.
- Blob: Individual file or object.

**Types of Blobs:**
- Block Blobs: Used for text and binary files, such as images and PDFs.
- Append Blobs: Optimized for appending data, such as application logs.
- Page Blobs: Designed for random read/write operations and commonly associated with virtual machine disk storage.

**Key consideration:** The storage type should be selected based on the application's data requirements and access patterns.

### 3. Azure Files

Azure Files provides fully managed cloud-based file shares that multiple machines or applications can access.

**When to use it:**
- Multiple virtual machines need access to the same shared files.
- An application depends on traditional network file shares.
- A team wants to migrate on-premises file-sharing solutions to Azure.

**Key features:**
- Supports SMB and NFS protocols.
- Provides shared file access.
- Can be accessed by multiple machines.
- Reduces the need to maintain traditional file servers.

**Key consideration:** Azure Files is useful when applications require shared file-system access rather than object-based storage.

### 4. Azure Queue Storage

Azure Queue Storage is used to store messages so different parts of an application can communicate asynchronously.

**Examples include:**
- Processing customer orders in the background.
- Handling application tasks without making users wait.
- Managing communication between application components.

**Key concepts:**
- Producer: Application that sends messages.
- Queue: Holds messages until they are processed.
- Consumer: Application that retrieves and processes messages.

**Key consideration:** Queue Storage supports asynchronous processing. The application components can work independently rather than waiting for each other to complete every task.

### 5. Azure Table Storage

Azure Table Storage is a NoSQL key-value data store used to store large amounts of structured, non-relational data.

**When to use it:**
- An application needs to store employee or customer metadata.
- A team needs flexible storage for simple structured records.
- An application requires scalable NoSQL key-value storage.

**Key concepts:**
- Table: Collection of entities.
- Entity: Individual record.
- Property: Attribute of an entity.
- Partition Key: Groups related entities.
- Row Key: Identifies an entity within a partition.

**Key consideration:** Table Storage does not require a traditional relational database schema. The combination of Partition Key and Row Key identifies an entity.

### 6. Azure Managed Disks

Azure Managed Disks provide persistent block-level storage for Azure Virtual Machines.

**When to use it:**
- A virtual machine needs storage for its operating system.
- An application running on a VM needs persistent data storage.
- A workload requires different disk performance levels.

**Common disk types:**
- Standard HDD: Cost-effective storage for less demanding workloads.
- Standard SSD: Suitable for moderate performance requirements.
- Premium SSD: Higher-performance storage for demanding workloads.
- Ultra Disk: Designed for workloads requiring very high performance.

**Key consideration:** Managed Disks provide storage for virtual machines, while Azure manages the underlying disk infrastructure.

## Relational vs. NoSQL Databases

### 7. Relational Databases (SQL)

Relational databases store data in structured tables containing rows and columns. Relationships can be established between tables.

**Key characteristics:**
- Structured data.
- Predefined schema.
- Relationships between tables.
- SQL queries.
- Supports transactions and data consistency.

**Azure example:** Azure SQL Database.

**Example:** An e-commerce application stores customer details and order information in separate tables connected through Customer ID.

### 8. NoSQL Databases

NoSQL databases support flexible data models and are useful for applications that require different ways of organizing and accessing data.

**Key characteristics:**
- Flexible data models.
- Supports structured and semi-structured data.
- Suitable for different scalability and access patterns.
- Does not require traditional relational table relationships.

**Azure examples:**
- Azure Cosmos DB.
- Azure Table Storage.

**Key consideration:** The choice between SQL and NoSQL depends on the application's data structure, consistency requirements, access patterns, and scalability needs.

## Comparing Azure Storage and Database Options

| Service | Main purpose | Example use case |
|---|---|---|
| Azure Blob Storage | Unstructured object storage | Images, videos, and documents |
| Azure Files | Shared file storage | Multiple servers accessing shared folders |
| Azure Queue Storage | Asynchronous messaging | Background order processing |
| Azure Table Storage | NoSQL key-value storage | Employee metadata |
| Azure Managed Disks | Virtual machine block storage | Operating system and application data |
| Azure SQL Database | Relational database | Customer and transaction records |
| Azure Cosmos DB | NoSQL database | Globally distributed applications |

These services are not interchangeable. An application might use Blob Storage for uploaded documents, Azure SQL Database for transactions, and Queue Storage for background processing.

## What I Learned

- Azure Storage provides different services for different data storage requirements.
- Blob Storage is suitable for unstructured data such as images, videos, and documents.
- Azure Files provides shared file access using SMB and NFS.
- Queue Storage enables asynchronous communication between application components.
- Table Storage provides NoSQL key-value storage.
- Managed Disks provide persistent storage for Azure Virtual Machines.
- Azure SQL Database is a relational database service.
- Azure Cosmos DB supports globally distributed NoSQL workloads.
- The appropriate storage or database service depends on application requirements, data structure, performance, and access patterns.

## Scrum Master Perspective

A Scrum Master does not need to configure Azure Storage or databases or solve every technical issue personally. However, understanding the basics of these services helps identify technical dependencies and facilitate effective conversations.

A Scrum Master can:
- Clarify the nature of a storage or database-related blocker.
- Identify the responsible technical owners, such as developers, database administrators, or cloud/DevOps engineers.
- Understand how the issue affects testing, data migration, dependencies, delivery timelines, and the Sprint Goal.
- Facilitate collaboration between the teams involved.
- Make impediments visible and follow up on their resolution.
- Support the team in assessing delivery risks without taking over specialized technical responsibilities.

## Practical Examples and Scenarios

### Scenario 1: Choosing a Storage Service

**Situation:** A team is developing an application where users upload profile pictures, PDF documents, and other files.

**Appropriate option:** Azure Blob Storage.

**Reason:** Blob Storage is designed for storing large amounts of unstructured data.

### Scenario 2: Shared File Access

**Situation:** A legacy application requires multiple virtual machines to access the same shared folder using SMB.

**Appropriate option:** Azure Files.

**Reason:** Azure Files provides managed file shares that can be accessed by multiple machines.

### Scenario 3: Background Order Processing

**Situation:** An e-commerce application needs to process customer orders in the background without making customers wait for the processing to finish.

**Appropriate option:** Azure Queue Storage.

**Reason:** Queue Storage enables asynchronous communication between the order application and background processing components.

### Scenario 4: NoSQL Data Storage

**Situation:** An application needs to store large volumes of structured, non-relational records without using a traditional relational database schema.

**Appropriate option:** Azure Table Storage.

**Reason:** Table Storage provides a NoSQL key-value data model using entities, Partition Keys, and Row Keys.

### Scenario 5: Virtual Machine Storage

**Situation:** An Azure Virtual Machine requires persistent storage for its operating system and application data.

**Appropriate option:** Azure Managed Disks.

**Reason:** Managed Disks provide persistent block-level storage for virtual machines.

### Scenario 6: Relational vs. NoSQL Database Selection

**Situation:** A team is evaluating database options for an application that requires globally distributed NoSQL data access.

**Potential approach:** Consider Azure Cosmos DB.

**Reason:** Cosmos DB supports globally distributed NoSQL workloads. The team should evaluate application requirements, consistency, latency, and data access patterns before selecting a database.

### Scenario 7: Database Migration Blocking Testing

**Situation:** A team is migrating data from an existing relational database to a NoSQL database. Data reconciliation failures are preventing testing from progressing.

**Scrum Master response:**
1. Clarify the migration issue and gather relevant information.
2. Identify the responsible technical owners.
3. Facilitate collaboration between development, database, and testing teams.
4. Make the impediment and its delivery impact visible.
5. Follow up and help the team assess the impact on the Sprint Goal.

**Key learning:** The Scrum Master enables problem-solving and removes organizational obstacles without needing to perform database configuration or migration activities personally.

## Interview Questions

1. What is Azure Storage, and why are different storage services available?
2. What is the difference between Azure Blob Storage and Azure Files?
3. What are the different types of Azure Blobs?
4. What is Azure Queue Storage, and why is it used?
5. Explain Producer and Consumer in queue-based processing.
6. What is Azure Table Storage?
7. What are Partition Key and Row Key?
8. What are Azure Managed Disks?
9. What is the difference between relational and NoSQL databases?
10. What is the difference between Azure SQL Database and Azure Cosmos DB?
11. How would you respond if a database migration issue blocked testing during a Sprint?
12. How can a Scrum Master help resolve storage and database dependencies without taking over the technical team's responsibilities?

## Validation and Reflection

**Validation Score:** 9/10 (90%)

The validation covered:
- Selecting appropriate Azure Storage services for different use cases.
- Understanding Blob types and shared file storage.
- Recognizing asynchronous message processing scenarios.
- Understanding Azure Managed Disks.
- Distinguishing relational and NoSQL databases.
- Identifying suitable Azure database services.
- Understanding Table Storage terminology.
- Applying the Scrum Master approach to cloud storage and database-related impediments.

**Reflection:** I can now distinguish between the main Azure Storage and Database services and explain how they support application delivery. I also understand how storage and database dependencies can affect testing, data migration, and the Sprint Goal. As a Scrum Master, my responsibility is to facilitate collaboration, make impediments visible, and support the team in resolving delivery challenges rather than taking over specialized technical work.

## Key Takeaways

- Select Azure Storage services according to the application's data requirements.
- Understand the difference between object storage, shared file storage, message queues, and VM disk storage.
- Understand when relational and NoSQL databases are appropriate.
- Storage and database dependencies can affect development, testing, and release activities.
- A Scrum Master helps the team make impediments visible, collaborate on resolution, and protect progress toward the Sprint Goal.

## Status

**Completed** — Lesson 4: Azure Storage & Databases

Learning cycle: Learn → Practice → Validate → Reflect → Share → Improve
