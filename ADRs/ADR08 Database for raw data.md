# ADR08. Database for raw data

**Status** : proposed

**Date** : 20.02.2024

**Stakeholders**

- [x] @vera-ignateva
- [x] @formalizator
- [x] @slookin
- [x] @alkhamov

## Context

In consideration of the following requirements:

- **[FR4]** - Monitoring data should be available during last 24 hours for the review
- **[FR5]** - Review of vital signs history is possible, filtering on time range as well as vital sign
- **[NFR1]** - System should continue to collect and display data regardless on any particular device availability
- **[NFR2]** - Monitoring data should not be corrupted by the system during processing
- **[NFR5]** - Maximum number of patients per physical MonitorMe instance: 500
- **[NFR7]** - System should be prepared to add new types of Patient-monitoring Devices
- **[NFR10]** - All raw data from all monitoring devices is stored in the system

We assume that we need a **separate database** for storing raw data.

To determine what database type we can use, we can count raw estimation of data gathered per patient:

| Characteristic   | Rate            | Records per 24h |
|------------------|-----------------|-----------------|
| Heart rate       | every 500ms     | 172800          |
| Blood pressure   | every hour      | 24              |
| Oxygen level     | every 5 seconds | 17280           |
| Blood sugar      | every 2 minutes | 720             |
| Respiration      | every second    | 86400           |
| ECG              | every second    | 86400           |         
| Body temperature | every 5 minutes | 288             |
| Sleep status     | every 2 minutes | 720             |

If we assume that we need 24 bytes for the raw record (device id, timestamp, value):
* Total data for 1 patient per 24h : 364632 records or 8.34 megabytes
* Total data for 500 patients per 24h : 182316000 records or 4.17 gigabytes

## Options

### Option 1: SQL Database

Use SQL solutions like PostgreSQL
* **Pros:** structured data storage, data integrity and consistency, data security, support for complex analytics
* **Cons:** require a predefined schema, scalability challenges, storage overhead
____

### Option 2: noSQL Database

Use noSQL solutions, like MongoDB
* **Pros:** flexible data model, scalability, high performance
* **Cons:** limited query capabilities
____

### Option 3: Time-Series Database

Use time-series databases, that are specifically designed for handling time-stamped data efficiently.

* **Pros:** optimized for time-series data, efficient storage and compression, high write throughput, time-ordered data retention, support for time-based queries
* **Cons:** suboptimal for non-time-series data, scalability challenges

#### InfluxDB

* **Pros:** designed specifically for time-series data. It has a user-friendly query language (InfluxQL). It offers high scalability and clustering capabilities.
* **Cons:** may require more resources (CPU, memory, disk) compared to TimescaleDB.

#### TimescaleDB

* **Pros:** is an extension of PostgreSQL, offering the familiarity of SQL for querying time-series data. It provides excellent scalability and performance, especially for analytical workloads. TimescaleDB is known for its data integrity features, making it suitable for IoT applications where data accuracy is crucial.
* **Cons:** offers strong SQL support, but may not be as optimized for certain real-time use cases compared to InfluxDB.
____

### Option 4: Apache Kafka

* **Pros:** a distributed event streaming platform, widely used for real-time data processing, offers high scalability, fault tolerance.
* **Cons:** requires additional components and configurations to function as a time-series database, which may add complexity to the setup, and may not offer the needed level of historical querying features.

## Decision

Taking into account all requirements, especially the possibility of high increase of the gathered data, we consider usage of a **Time-Series Database**. 

Among Time-Series Databases, InfluxDB looks a good solution, but some experiments may be needed.

## Consequences

- Solution with a separate DB improves availability and robustness of the system
- Using of a time-series database improves evolvability of the system
- There may be associated costs with maintenance and support
