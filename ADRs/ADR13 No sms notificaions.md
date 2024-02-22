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
there are no implicit requests for SMS notifications.
For mobile devices, push notifications are requested.
We should also provide cost-optimised solution.

## Decision

SMS notifications are not needed in the system. 

## Consequences

Some of the notifications might be delivered with delay in case of bad hospital network connection or push-gateway delays.
