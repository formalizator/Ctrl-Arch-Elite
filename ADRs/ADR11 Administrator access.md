# ADR Title

**Status** : proposed

**Date** : 20.02.2024

**Stakeholders**

- [x] @vera-ignateva
- [x] @formalizator
- [x] @slookin
- [x] @alkhamov

## Context

In consideration of the following use cases:

- **[UC02]** - Register Medical staff in system
- **[UC03]** - Assign access roles to Medical staff
- **[UC04]** - Mapping Devices

We assume that administrator access is needed in the system.

## Decision

- Provide administrator access with a special role in IAM system
- Develop an admin functionality within the application

## Consequences

Implementing of admin functionality incurs additional costs related to development, infrastructure, and maintenance
