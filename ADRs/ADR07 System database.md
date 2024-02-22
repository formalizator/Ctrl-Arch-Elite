# ADR07 System database

**Status** : proposed

**Date** : 20.02.2024

**Stakeholders**

- [x] @vera-ignateva
- [x] @formalizator
- [x] @slookin
- [x] @alkhamov

## Context

In consideration of the following requirements:

- **[FR2]** - Display data from monitoring devices on monitoring screen per nurse station
- **[FR3]** - Display data rotating between patients every 5 seconds
- **[FR6]** - System analyzes each patient’s vital signs
- **[FR9]** - Alerts received on mobile app and displayed on monitoring screen as well
- **[FR10]** - Generate holistic snapshots from a patients consolidated vital signs at any time

We assume that patient management is needed in the system as well as storage of the current state that is consumed by Medical staff.

## Decision

We consider using relation DB for this kind of data.

* **Pros:** structured data storage, data integrity and consistency, data security
* **Cons:** require a predefined schema, limited support for unstructured data

PostgreSQL can be selected as a popular choice among relational database management systems

* **Pros:** an open-source project with a strong and active community, cross-platform compatibility, good performance
* **Cons:** vendor lock-in

## Consequences

- The company can have confidence in the reliability of its data
- PostgreSQL has a vibrant community and ecosystem with a wide range of tools, extensions, and support available
- PostgreSQL has a strong track record of stability and is backed by a large community and commercial support options
- Relation DBs require careful schema design and normalization to maintain data integrity and optimize performance
- There may be associated costs with maintenance and support.
