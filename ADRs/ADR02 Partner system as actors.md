# ADR Title

**Status** : proposed / accepted / superseded

**Date** : 20.02.2024

**Stakeholders**

- [ ] @vera-ignateva
- [ ] @formalizator
- [ ] @slookin
- [ ] @alkhamov

## Context
Identify partnering systems roles within the business context.
There are two partnering systems identified from the *Business problem* description:
- **MonitorThem**
- **MyMedicalData**

Monitoring devices are also entities which behavior may be described as external in relation to the designed system

## Decision
Due to the following criteria:
- necessity to handle the requirements from/to the mentioned external systems
- separate responsibilities of the external systems
- highlight the integration patterns between the external systems and designed system
both mentioned external systems to be considered as a primary actors in relation to MonitorMe system while defining use cases of the designing system.
Monitoring devices in the same context to be considered as secondary actors.

## Consequences
MonitorME *Provide snapshot* use case has MyMonitoringData system as an actor which accepts monitoring data.
Monitoring devices in relation to main use case *Collect vital signs* of MonitorMe system plays the role of the secondary actor.
