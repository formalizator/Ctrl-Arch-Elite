# Functional Requirements

Functional requirements are derived from input given by the stakeholders documented
there [Problem Description document](01_Problem_description.md).

| #    | Requirement                                                                              |
|------|------------------------------------------------------------------------------------------|
| FR1  | Collect data from monitoring devices. See [Device list](#device-list).                   |
| FR2  | Display data from monitoring devices on monitoring screen per nurse station              |
| FR3  | Display data rotating between patients every 5 seconds                                   |
| FR4  | Monitoring data should be available during last 24 hours for the review                  |
| FR5  | Review of vital signs history is possible, filtering on time range as well as vital sign |
| FR6  | System analyzes each patient’s vital signs                                               |
| FR7  | Send alert in case of any vital sign value is out of regular range                       |
| FR8  | Regular range value (alert thresholds) depends on patient sleep state                    |
| FR9  | Alerts received on mobile app and displayed on monitoring screen as well                 |
| FR10 | Generate holistic snapshots from a patients consolidated vital signs at any time         |
| FR11 | Upload the patient snapshot to MyMedicalData                                             |

## Device list

Each patient monitoring device transmits vital sign readings at a different rate:

* Heart rate: every 500ms
* Blood pressure: every hour
* Oxygen level: every 5 seconds
* Blood sugar: every 2 minutes
* Respiration: every second
* ECG: every second
* Body temperature: every 5 minutes
* Sleep status: every 2 minutes

# Non-functional Requirements

Non functional requirements are derived from functional requiremetns and busienss context.

### Robustness/Fault tolerance

* [NFR1] System should continue to collect and display data withregardless on any particular device
  availability.

### Reliability

* [NFR2] Monitoring data should not be corrupted by the system during processing and should have precise cohesion to
  the coupled data managed by other system

### Scalability/Elasticity

* [NFR3] There is a maximum of 20 patients per nurses station.
* [NFR4] Maximum number of patients per physical MonitorMe instance: 500
* [NFR5] The system should be elastic when adding/removing new hospitals. (Change data volume, traffic and computing
  units)

### Perfomance

* [NFR6]  Monitoring device data should be available for visualisation or alerting within less than 1 second.

### Evolvability

* [NFR7] System should be prepared to add new type of Patient-monitoring Device should be efficient in terms of cost
  and time
* [NFR8] System should be prepared to add/delete new functionality as we expect a lot of changes.

### Security/Privacy

* [NFR9] Patient related data should not be available for the audience which it is not intended to

## Requirements matrix

| FR/TR  | Availability | Scalability | Performance | Consistency | Cost | Evolvability | Usability | Reliability | Robustness | Security |
|--------|--------------|-------------|-------------|-------------|------|--------------|-----------|-------------|------------|----------|
| [FR1]  |              |             |             |             |      |              |           |             |            |          |
| [FR2]  |              |             |             |             |      |              |           |             |            |          |
| [FR3]  |              |             |             |             |      |              |           |             |            |          |
| [FR4]  |              |             |             |             |      |              |           |             |            |          |
| [FR5]  |              |             |             |             |      |              |           |             |            |          |
| [FR6]  |              |             |             |             |      |              |           |             |            |          |
| [FR7]  |              |             |             |             |      |              |           |             |            |          |
| [FR8]  |              |             |             |             |      |              |           |             |            |          |
| [FR9]  |              |             |             |             |      |              |           |             |            |          |
| [FR10] |              |             |             |             |      |              |           |             |            |          |
| [FR11] |              |             |             |             |      |              |           |             |            |          |
| [NFR1] |              |             |             |             |      |              |           |             |            |          |
| [NFR2] |              |             |             |             |      |              |           |             |            |          |
| [NFR3] |              |             |             |             |      |              |           |             |            |          |
| [NFR4] |              |             |             |             |      |              |           |             |            |          |
| [NFR5] |              |             |             |             |      |              |           |             |            |          |
| [NFR6] |              |             |             |             |      |              |           |             |            |          |
| [NFR7] |              |             |             |             |      |              |           |             |            |          |
| [NFR8] |              |             |             |             |      |              |           |             |            |          |
| [NFR9] |              |             |             |             |      |              |           |             |            |          |

# Architecture Characteristics

| Top 3 | # | Driving Characteristics | 
|-------|---|-------------------------|
| x     | 1 | Availability            |
|       | 2 | Consistency             |
| x     | 3 | Evolvability            |
|       | 5 | Reliability             |
| x     | 6 | Robustness              |
|       | 7 | Security                |

| # | Implicit Characteristics |
|---|---------------------|
| 1 | Usability           |
| 2 | Simplicity          |

| # | Others considered |
|---|-------------------|
| 1 | Cost              |

# Actors

надо проверить список акторов, сделать приятное описание, и проставить ссылки на UC (которые описаны в главе ниже)

| Actor                     | Description                                                                                                  | Use Case Reference  |
|---------------------------|--------------------------------------------------------------------------------------------------------------|---------------------|
| Patient                   | Produce metrics via monitoring device trips.                                                                 | no system use cases |
| Medical Staff             | Including Nurses.                                                                                            |                     |
| Medical Professionals     | Including doctors.                                                                                           |                     |
| Administrator             | Dedicated role in Medical Professionals/Staff or external employer, who responsible for configuration system |                     | 
| Patient-monitoring Device | System Actor Patient-monitoring Device to deliver vital sign.                                                |
| MyMedicalData             | System Actor MyMedicalData is a comprehensive cloud-based patient medical records                            |
| System                    | Some activities are initiated by the system internally.                                                      |

# Use Cases

надо проверить список сценариев, сделать приятное описание, и проставить ссылки на Акторов (проверить что они совпадают
с таблицой выше)

| #    | Use Case                               | Short Description                                                                        | Actor                                 | Requirement |
|------|----------------------------------------|------------------------------------------------------------------------------------------|---------------------------------------|-------------|
| UC01 | Login into system                      | User logs in into the system.                                                            | Medical Staff / Medical Professionals |             |
| UC02 | Register Medical staff in system       | Registers Medical Staff and Medical Professionals in system.                             | Administrator                         |             |
| UC03 | Assign access roles to Medical staff   | Assign access roles to Medical staff in the system.                                      | Administrator                         |             |
| UC04 | Mapping Devices                        | Configure system by adding new devices and mapping them to "patient bed" and Nurses      | Administrator                         |             |
| UC05 | Register Patient in system             | Registers Patient and assign him to "bed" and to Doctor                                  | Medical Staff                         |             |
| UC06 | Collect vital sign                     | System collect vital signs from patient-monitoring devices.                              | System, Patient-monitoring Device     |             |
| UC07 | Monitor patient vital status           | Nurse able to monitor all vital signs from patients                                      | Medical Staff, Patient                |             |
| UC08 | Configure Thresholds                   | Configure thresholds for different types on vital sign (also interdependent signs)       | Administrator                         |             |
| UC09 | Receive Alert notification             | Medical Staff receive notification if any thresholds achieved                            | System, Medical Professionals         |             |
| UC10 | Generate vital sings snapshot          | Medical Professionals configure snapshot of data and data stored in MyMedicalData system | Medical Professionals                 |             |
| UC11 | Analyse historical vital data          | Medical Professionals can view, filter vital sign history in frame of 24h                | Medical Professionals                 |             |
| UC12 | Managing Hospitals/MonitorMe Instances | StayHealthy technical staff able to provision new Hospital/MonitorMe instance            | Administrator                         |             |
| UC13 | Discharge patient                      | Unassign patient from "bed" and from Doctor                                              | Medical Staff                         |             |

