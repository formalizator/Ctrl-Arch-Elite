# ADR Title

**Status** : proposed / accepted / superseded

**Date** : 20.02.2024

**Stakeholders**

- [ ] @vera-ignateva
- [ ] @formalizator
- [ ] @slookin
- [ ] @alkhamov

## Context
Medical staff and medical professional these two types of actors mentioned separately within the *Business problem* description. Consider the possibility to merge them.

## Decision
From the *Business problem* statements we have Medical staff who has separate behavior covered by the use case "Provide snapshot" in comparison to the Medical professional who are generalization of "Doctor" and "Nurse" actors.  
However, due to the decision of applying out-of-the-box IAM system users will be segregated based on predefined authentication privileges.  
Therefore to simplify the *System context* diagram the decision is to merge actors.

## Consequences
From solution perspective generalization of medical personal simplifies user management by the system enhancing the security at the same time.
