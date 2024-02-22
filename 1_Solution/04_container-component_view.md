# Detailed system views

Deployment diagrams that help with understanding of system deployment and modules. 

## MonitorMe - Container diagram

Container Diagram provides a high-level view of the software architecture, focusing on the containers that house the software components. These containers represent runtime environments such as applications, databases, or services, and illustrate how they interact with each other. In the context of MonitorMe, the Container Diagram would depict the various containers involved in the system, including components like the web application, mobile application, databases, external services, and any other significant software entities. Each container would be labeled and annotated to convey its purpose, technology stack, and dependencies, providing stakeholders with a clear understanding of the system's overall structure and the relationships between its components. This diagram serves as a valuable tool for communication and collaboration among development teams, architects, and other stakeholders involved in the design and implementation of the MonitorMe system.

![Container diagram](./../images/container-diagram.drawio.png "Container diagram")

| Name                                                              | Description                                                                                      | Hosting |
|-------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|---------|
| [**MonitorMe Hospital**](#monitorme-hospital---component-diagram) | The heart of our system that is hosted inside of the hospitals.                                  | On-Prem |
| **Raw Database**                                                  | Database for storage of the raw data.                                                            | On-Prem |
| **Snapshot Database**                                             | Database for storage of the current state that is consumed by Medical staff.                     | On-Prem |
| **MonitorMe MobileNotify**                                        | Central push-gateway for all of the hospitals. Main functionality - distribute the notification. | Cloud   |

## MonitorMe Hospital - Component diagram

Container that deployed to the Hospital infrastructure locally consists of several components.
They have strict functionality assignment and can be decomposed in separate containers in future for scaling purposes.
In the C4 Component View for the "MonitorMe Hospital" container, we delve into the internal architecture of this pivotal component within the MonitorMe ecosystem. At its core lies the application logic orchestrating patient data management, monitoring parameters, and insights generation, serving as the central hub for hospital-based operations. Complementary components include user interfaces tailored for clinicians and administrative personnel, alongside integration modules ensuring seamless interoperability with existing hospital systems. Database systems within the container store and manage patient records, monitoring data, and configurations, bolstered by robust security measures to uphold patient privacy and regulatory compliance. This view provides stakeholders with a succinct yet comprehensive understanding of the "MonitorMe Hospital" container's structure, functionality, and integration points, facilitating effective collaboration and decision-making in system development and deployment.

![Component diagram](./../images/component-diagram-monitorme-hospital.drawio.png "Component diagram")

To save compute resource and optimize performance we use in-app direct calls across modules.

| Name                       | Descripton                                                                | Type        |
|----------------------------|---------------------------------------------------------------------------|-------------|
| **Device Receiver module** | Component that receives data directly from monitoring devices.            | Java module |
| **State Machine**          | Component that merges raw data and notifies about new status              | Java module |
| **Web UI**                 | Set of UI for different use-cases. Such as nurse station or doctor visit. | Java module |
