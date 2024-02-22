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

- **[FR5]** - Review of vital signs history is possible, filtering on time range as well as vital sign
- **[FR10]** - Generate holistic snapshots from a patients consolidated vital signs at any time

And with assumption that medical staff may need to access cloud-based solution MyMedicalData and MonitorThem, 
we assume that we need to configure up to 25 computer devices on nurse stations in the hospital, independent of monitoring screens.

## Decision

We can use workstations and web browsers to access MonitorMe system, as well as other StayHealthy, Inc. systems.

## Consequences

- Developing and maintaining a web-based service is cost-effective compared to building and updating separate native applications.
- Web-based services can be updated centrally, ensuring all users have access to the latest version simultaneously.
- Browsers can store user data such as browsing history, cookies, and cached files, which may raise concerns about data privacy - admins need to manage their privacy settings.
