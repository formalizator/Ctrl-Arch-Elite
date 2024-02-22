# ADR Title

**Status** : proposed

**Date** : 20.02.2024

**Stakeholders**

- [x] @vera-ignateva
- [x] @formalizator
- [x] @slookin
- [x] @alkhamov

## Context

In consideration of the following requirement:

- **[FR9]** - Alerts received on mobile app and displayed on monitoring screen as well

we need a solution for mobile push notifications.

## Decision

We can use cloud-based solution for push notifications, depending on the infrastructure of existing cloud-based solutions:
- Amazon: [AWS SNS](https://aws.amazon.com/sns/)
- GCP: [Pub/Sub](https://cloud.google.com/pubsub) and [FCM](https://firebase.google.com/docs/cloud-messaging)
- Azure: [Notification Hub](https://azure.microsoft.com/en-us/services/notification-hubs/), [Event Grid](https://azure.microsoft.com/en-us/services/event-grid/)

## Consequences
- Leveraging a specific push notification service can simplify development and management tasks
- Low latency for delivering notifications to mobile devices
- May come with additional costs due to the distributed infrastructure required
