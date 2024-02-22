# ADR07 Database for processing

**Status** : proposed

**Date** : 20.02.2024

**Stakeholders**

- [x] @vera-ignateva
- [ ] @formalizator
- [ ] @slookin
- [ ] @alkhamov

## Context

In consideration of the following requirements:

- **[FR2]** - Display data from monitoring devices on monitoring screen per nurse station
- **[FR3]** - Display data rotating between patients every 5 seconds
- **[FR6]** - System analyzes each patient’s vital signs
- **[FR9]** - Alerts received on mobile app and displayed on monitoring screen as well
- **[FR10]** - Generate holistic snapshots from a patients consolidated vital signs at any time

We assume that patient management is needed in the system.

## Decision

We consider using relation DB like PostgreSQL for this kind of data.

* **Pros:** structured data storage, data integrity and consistency, data security
* **Cons:** require a predefined schema, limited support for unstructured data

## Consequences

TODO