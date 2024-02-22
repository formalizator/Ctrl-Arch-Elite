# ADR Title

**Status** : proposed / accepted / superseded

**Date** : 20.02.2024

**Stakeholders**

- [x] @vera-ignateva
- [x] @formalizator
- [x] @slookin
- [x] @alkhamov

## Context

Requirements naming specification should be transparent and easy to maintain.

From the following options we have to decide which standard fits better to our needs:
- **IEEE 830**
- **IBM Rational Unified Process (RUP)**
- **Verb-Noun Format**
- **ISO/IEC/IEEE 29148**
- **Custom business domain specific naming** 


## Decision
**IEEE 830** was chosen due to its clarity and transparency in terms of future maintenance (extensibility support), easy mapping to the different use cases.

## Consequences
Simple traceability to different levels of the solution abstractions especially in cooperation with C4 notation.
Straightforward extension of the requirement matrix with newly added requirements with regardless to the solution context level
