# ADR Title

**Status** : proposed

**Date** : 20.02.2024

**Stakeholders**

- [x] @vera-ignateva
- [x] @formalizator
- [x] @slookin
- [x] @alkhamov

## Context

Based on list of all functional and non-functional [requirements](../0_Requirements/03_Requirements.md),
there are no implicit requests for e-mail notifications.
All interactions with user login and reporting are outside the scope of current system.

## Decision

E-mail notifications are not needed in the system.

## Consequences

- No option for mail communication with the customer
- Lower maintenance efforts
- In case of the system extension, additional firewall clearance and components need to be designed.
