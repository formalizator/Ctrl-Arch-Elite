# ADR Title

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
- **[FR9]** - Alerts received on mobile app and displayed on monitoring screen as well

We assume that we need to configure up to 25 monitoring screens in the hospital.

## Decision

We can use monitoring screens with browser and web application on each screen for displaying patient monitoring data.

* **Pros:** can be easily updated and customized, remote management and content updates are possible, can incorporate interactive elements
* **Cons:** possible performance issues for complex web applications, system updates could potentially disrupt the display process

## Consequences

TODO