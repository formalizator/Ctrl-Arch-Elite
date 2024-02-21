**Status** : proposed 

**Date** : 21.02.2024

**Stakeholders**

- [ ] @vera-ignateva
- [ ] @formalizator
- [ ] @slookin
- [ ] @alkhamov


# ADR 1: Where store 24h data?

**Context:** MonitorMe need to store 24h data for up to 500 patient.

## Options

### Option 1: Store locally in hospital

**Pro:** Secure, privacy

**Cons:** Cost for hardware, need to thiniking about HA and backups
____

### Option 2: Store in central cloud

**Pro:** central scalabale storage, HA, backups out of box, easy to sent snapshot to MyMedicData

**Cons:** privacy, need to be sure that all data reach cloud, connectivity between Hospital and Cloud, can affect perfomance for Medical Staff (not affect Nurses).

## Decision
TODO

## Concequences
TODO