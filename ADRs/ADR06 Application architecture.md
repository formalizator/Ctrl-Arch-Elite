# ADR Title

**Status** : proposed / accepted / superseded

**Date** : 20.02.2024

**Stakeholders**

- [x] @vera-ignateva
- [x] @formalizator
- [x] @slookin
- [x] @alkhamov

## Context
Considering given architectural characteristics we left with the choice of two architectural approaches:
- **Monolithic Architecture **
- **Microservices Architecture **

## Decision
Application architecture sticks to "Modular monolith".  
Modular monolith combines the benefits of a monolithic architecture with modular design. Such monolith encapsulates loosely coupled functions within one deployment artifact.

## Consequences
Taking the system robustness, recoverability and performance as a top architectural characteristics, monolithic architecture ensures fast recovery time from disaster, limited number of possible security breaches to maintain and simple operations and maintenance.  
Moreover, due to the modular approach system will be easily scalable, elastic and provide the possibility for future partitioning when necessary.
