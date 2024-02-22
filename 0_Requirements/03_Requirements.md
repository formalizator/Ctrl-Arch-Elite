# Requirements decomposition

## Functional Requirements

Functional requirements are derived from input given by the stakeholders documented
there [Problem Description document](01_Problem_description.md).

| #                       | Requirement                                                                                                   |
|-------------------------|---------------------------------------------------------------------------------------------------------------|
| <a name="FR1"></a>FR1   | Collect data from monitoring devices. See [Device list](#device-list).<sup>[[DESC4]](./01_Problem_description.md#DESC4)</sup>                                        |
| <a name="FR2"></a>FR2   | Display data from monitoring devices on monitoring screen per nurse station<sup>[[DESC5]](./01_Problem_description.md#DESC5)</sup>                                   |
| <a name="FR3"></a>FR3   | Display data rotating between patients every 5 seconds<sup>[[DESC5]](./01_Problem_description.md#DESC5)</sup> |
| <a name="FR4"></a>FR4   | Monitoring data should be available during last 24 hours for the review<sup>[[DESC6]](./01_Problem_description.md#DESC6)</sup>                                       |
| <a name="FR5"></a>FR5   | Review of vital signs history is possible, filtering on time range as well as vital sign<sup>[[DESC6]](./01_Problem_description.md#DESC61)</sup>                      |
| <a name="FR6"></a>FR6   | System analyzes each patient’s vital signs<sup>[[DESC7]](./01_Problem_description.md#DESC7)</sup>                                                                    |
| <a name="FR7"></a>FR7   | Send alert in case of any vital sign value is out of regular range<sup>[[DESC7]](./01_Problem_description.md#DESC7)</sup>                                            |
| <a name="FR8"></a>FR8   | Regular range value (alert thresholds) depends on patient sleep state<sup>[[DESC7]](./01_Problem_description.md#DESC7)</sup>                                         |
| <a name="FR9"></a>FR9   | Alerts received on mobile app and displayed on monitoring screen as well<sup>[[DESC10]](./01_Problem_description.md#DESC10)</sup>                                      |
| <a name="FR10"></a>FR10 | Generate holistic snapshots from a patients consolidated vital signs at any time<sup>[[DESC22]](./01_Problem_description.md#DESC22)</sup>                             |
| <a name="FR11"></a>FR11 | Upload the patient snapshot to MyMedicalData<sup>[[DESC22]](./01_Problem_description.md#DESC22)</sup>                                                                  |

### Device list

Each patient monitoring device transmits vital sign readings at a different rate:<sup>[[DESC13]](./01_Problem_description.md#DESC13)</sup>

* Heart rate: every 500ms<sup>[[DESC14]](./01_Problem_description.md#DESC14)</sup>
* Blood pressure: every hour<sup>[[DESC15]](./01_Problem_description.md#DESC15)</sup>
* Oxygen level: every 5 seconds<sup>[[DESC16]](./01_Problem_description.md#DESC16)</sup>
* Blood sugar: every 2 minutes<sup>[[DESC17]](./01_Problem_description.md#DESC17)</sup>
* Respiration: every second<sup>[[DESC18]](./01_Problem_description.md#DESC18)</sup>
* ECG: every second<sup>[[DESC19]](./01_Problem_description.md#DESC19)</sup>
* Body temperature: every 5 minutes<sup>[[DESC20]](./01_Problem_description.md#DESC20)</sup>
* Sleep status: every 2 minutes<sup>[[DESC21]](./01_Problem_description.md#DESC21)</sup>

## Non-functional Requirements

Non functional requirements are derived from functional requirements and business context.

### Robustness/Fault tolerance

* <a name="NFR1"></a>[NFR1] System should continue to collect and display data regardless on any particular device
  availability.<sup>[[DESC11]](./01_Problem_description.md#DESC11)</sup>

### Reliability

* <a name="NFR2"></a>[NFR2] Monitoring data should not be corrupted by the system during processing and should have
  precise cohesion to the coupled data managed by other system

### Scalability/Elasticity

* <a name="NFR3"></a>[NFR3] There is a maximum of 20 patients per nurses station.<sup>[[DESC5]](./01_Problem_description.md#DESC5)</sup>
* <a name="NFR4"></a>[NFR4] Maximum number of patients per physical MonitorMe instance: 500<sup>[[DESC23]](./01_Problem_description.md#DESC23)</sup>
* <a name="NFR5"></a>[NFR5] The system should be elastic when adding/removing new hospitals. (Change data volume,
  traffic and computing units)<sup>[[DESC25]](./01_Problem_description.md#DESC25)</sup>

### Perfomance

* <a name="NFR6"></a>[NFR6]  Monitoring device data should be available for visualisation or alerting within less than 1
  second.<sup>[[DESC5]](./01_Problem_description.md#DESC5)</sup>

### Evolvability

* <a name="NFR7"></a>[NFR7] System should be prepared to add new type of Patient-monitoring Device should be efficient
  in terms of cost and time
* <a name="NFR8"></a>[NFR8] System should be prepared to add/delete new functionality as we expect a lot of changes.

### Security/Privacy

* <a name="NFR9"></a>[NFR9] Patient related data should not be available for the audience which it is not intended to
* <a name="NFR9"></a>[NFR10] All raw data from all monitoring devices is stored in the system

## Requirements matrix

| FR/TR         | Availability | [Scalability](#scalabilityelasticity) | [Performance](#perfomance) | Consistency | Cost | [Evolvability](#evolvability) | Usability | [Reliability](#reliability) | [Robustness](#robustnessfault-tolerance) | [Security](#securityprivacy) |
|---------------|--------------|-------------|-------------|-------------|------|--------------|-----------|-------------|------------|----------|
| [FR1](#FR1)   |              |             |             |             |      |              |           |             |            |          |
| [FR2](#FR2)   |              |             |             |             |      |              |           |             |            |          |
| [FR3](#FR3)   |              |             |             |             |      |              |           |             |            |          |
| [FR4](#FR4)   |              |             |             |             |      |              |           |             |            |          |
| [FR5](#FR5)   |              |             |             |             |      |              |           |             |            |          |
| [FR6](#FR6)   |              |             |             |             |      |              |           |             |            |          |
| [FR7](#FR7)   |              |             |             |             |      |              |           |             |            |          |
| [FR8](#FR8)   |              |             |             |             |      |              |           |             |            |          |
| [FR9](#FR9)   |              |             |             |             |      |              |           |             |            |          |
| [FR10](#FR10) |              |             |             |             |      |              |           |             |            |          |
| [FR11](#FR11) |              |             |             |             |      |              |           |             |            |          |
| [NFR1](#FR1)  |              |             |             |             |      |              |           |             |            |          |
| [NFR2](#FR2)  |              |             |             |             |      |              |           |             |            |          |
| [NFR3](#FR3)  |              |             |             |             |      |              |           |             |            |          |
| [NFR4](#FR4)  |              |             |             |             |      |              |           |             |            |          |
| [NFR5](#FR5)  |              |             |             |             |      |              |           |             |            |          |
| [NFR6](#FR6)  |              |             |             |             |      |              |           |             |            |          |
| [NFR7](#FR7)  |              |             |             |             |      |              |           |             |            |          |
| [NFR8](#FR8)  |              |             |             |             |      |              |           |             |            |          |
| [NFR9](#FR9)  |              |             |             |             |      |              |           |             |            |          |

## Architecture Characteristics

| Top 3 | # | Driving Characteristics |
|-------|---|-------------------------|
| x     | 1 | Availability            |
|       | 2 | Consistency             |
| x     | 3 | Evolvability            |
|       | 5 | Reliability             |
| x     | 6 | Robustness              |
|       | 7 | Security                |

| # | Implicit Characteristics |
|---|--------------------------|
| 1 | Usability                |
| 2 | Simplicity               |

| # | Others considered |
|---|-------------------|
| 1 | Cost              |

## Actors

| Actor                     | Description                                                                                                  | Use Case Reference  |
|---------------------------|--------------------------------------------------------------------------------------------------------------|---------------------|
| Patient                   | Produce metrics via monitoring device trips.                                                                 | no system use cases |
| Medical Staff             | Including Nurses.                                                                                            |                     |
| Medical Professionals     | Including doctors.                                                                                           |                     |
| Administrator             | Dedicated role in Medical Professionals/Staff or external employer, who responsible for configuration system |                     |
| Patient-monitoring Device | System Actor Patient-monitoring Device to deliver vital sign.                                                |                     |
| MyMedicalData             | System Actor MyMedicalData is a comprehensive cloud-based patient medical records                            |                     |
| System                    | Some activities are initiated by the system internally.                                                      |                     |

### Patient

![Patient](./../images/actor-patient.drawio.png "Patient")

### Medical Staff and Medical Professionals

![Medical Staff and Medical Professionals](./../images/actor-medicals.drawio.png "Medical Staff and Medical Professionals")

### Administrator

![Administrator](./../images/actor-admin.drawio.png "Administrator")

### Patient-monitoring Device

![Patient-monitoring Device](./../images/actor-monitoring-device.drawio.png "Patient-monitoring Device")

### MyMedicalData

![MyMedicalData](./../images/actor-my-medical-data.drawio.png "MyMedicalData")

## Use Cases

| #                       | Use Case                               | Short Description                                                                        | Actor                                        | Requirement |
|-------------------------|----------------------------------------|------------------------------------------------------------------------------------------|----------------------------------------------|-------------|
| <a name="UC01"></a>UC01 | Login into system                      | User logs in into the system.                                                            | [Medical Staff / Medical Professionals](#medical-staff-and-medical-professionals)       |             |
| <a name="UC02"></a>UC02 | Register Medical staff in system       | Registers Medical Staff and Medical Professionals in system.                             | [Administrator](#administrator)                                |             |
| <a name="UC03"></a>UC03 | Assign access roles to Medical staff   | Assign access roles to Medical staff in the system.                                      | [Administrator](#administrator)                                |             |
| <a name="UC04"></a>UC04 | Mapping Devices                        | Configure system by adding new devices and mapping them to "patient bed" and Nurses      | [Administrator](#administrator)                                |             |
| <a name="UC05"></a>UC05 | Register Patient in system             | Registers Patient and assign him to "bed" and to Doctor                                  | [Medical Staff](#medical-staff-and-medical-professionals)                                |             |
| <a name="UC06"></a>UC06 | Collect vital sign                     | System collect vital signs from patient-monitoring devices.                              | [Patient-monitoring Device](#patient)             |             |
| <a name="UC07"></a>UC07 | Monitor patient vital status           | Nurse able to monitor all vital signs from patients                                      | [Medical Staff](#medical-staff-and-medical-professionals), [Patient](#patient)                       |             |
| <a name="UC08"></a>UC08 | Configure Thresholds                   | Configure thresholds for different types on vital sign (also interdependent signs)       | [Administrator](#administrator)                                |             |
| <a name="UC09"></a>UC09 | Receive Alert notification             | Medical Staff receive notification if any thresholds achieved                            | [Medical Professionals](#medical-staff-and-medical-professionals)                |             |
| <a name="UC10"></a>UC10 | Generate vital sings snapshot          | Medical Professionals configure snapshot of data and data stored in MyMedicalData system | [Medical Professionals](#medical-staff-and-medical-professionals), MyMedicalData |             |
| <a name="UC11"></a>UC11 | Analyse historical vital data          | Medical Professionals can view, filter vital sign history in frame of 24h                | [Medical Professionals](#medical-staff-and-medical-professionals)                        |             |
| <a name="UC12"></a>UC12 | Managing Hospitals/MonitorMe Instances | StayHealthy technical staff able to provision new Hospital/MonitorMe instance            | [Administrator](#administrator)                                |             |
| <a name="UC13"></a>UC13 | Discharge patient                      | Unassign patient from "bed" and from Doctor                                              | [Medical Staff](#medical-staff-and-medical-professionals)                                |             |
