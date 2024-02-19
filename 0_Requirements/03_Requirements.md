# Functional Requirements
Functional requirements are derived from input given by the stakeholders documented there [Problem Description document](01_Problem_description.md).


| #    | Requirement                                                                                                                                                 |
| ---- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| FR1  | System should collect |
| FR2  | |
| FR3  | |
| FR4  | |
| FR5  | |
| FR6  | |
| FR7  | |
| FR8  | |
| FR9  | |
| FR10 | |
| FR11 | |
| FR12 | 


# Non-functional Requirements

Non functional requirements are derived from functional requiremetns and busienss context.

### Robustness/Fault tolerance
* [NFR XX] System should continute to collect and display data data withregardless on any particular device availability.

### Reliability
* [NFR XX] Monitoring data should not be corrupted by the system during processing and should have precise cohesion to the coupled data managed by other system


### Scalability/Elasticity
* [NFR XX] There is a maximum of 20 patients per nurses station.
* [NFR XX] Maximum number of patients per physical MonitorMe instance: 500
* [NFR XX] The system should be elastic when adding/removing new hospitals. (Change data volume, traffic and computing units)

### Perfomance
* [NFR XX]  Monitoring device data should be available for visualisation or alerting within less than 1 second.
 

### Evolvability
* [NFR XX] System should be prepared to add new type of Patient-monitoring Device should be efficient in terms of cost and time
* [NFR XX] System should be prepared to add/delete new functionality as we expect a lot of changes.
 
  
### Security/Privacy
* [NFR XX] Patient related data should not be available for the audience which it is not intended to
  

## Requirements matrix

| FR/TR  | Availability | Scalability | Performance | Consistency | Cost | Evolvability | Useability | other-important-ility |
| ------ | ------------ | ----------- | ----------- | ----------- | ---- | ------------ | ---------- |-----------------------|
| [FR1]  |              |             |             |             |     |             |            |
| [FR2]  |              |             |             |             |      |             |            |
| [FR3]  |              |             |             |             |      |             |            |
| [FR4]  |              |             |             |             |      |            |            |
| [FR5]  |              |             |             |           |      |              |            |
| [FR6]  |              |             |             |            |      |              |            |
| [FR7]  |              |             |             |             |      |             |            |
| [FR8]  |              |             |             |             |      |             |           |
| [FR9]  |              |             |             |            |      |              |            |
| [FR10] |              |             |             |            |      |            |            |
| [FR11] |              |             |             |             |      |            |            |
| [FR12] |              |             |             |             |      |            |            |
| [NFR1]  |              |             |             |             |      |             |            |
| [NFR2]  |              |            |             |             |      |              |            |



# Actors

надо проверить список акторов, сделать приятное описание, и проставить ссылки на UC (которые описаны в главе ниже)

| Actor                        | Description                                                                                                                               | Use Case Reference                                         |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------- |
| Patient                      | Produce metrics via monotiring device trips.                                                                                              | no system use cases|
| Medical Staff                | Including Nurses.                                                                                                                         | |
| Medical Professionals        | Including doctors.                                                                                                                        | |
| Administrator    | Dedicated role in Medical Professionals/Staff or external employer, who responsible for configuration system                                          | | 
| Patient-monitoring Device    | System Actor Patient-monitoring Device to deliver vital sign.                                                                             |  
| MyMedicalData                | System Actor MyMedicalData is a comprehensive cloud-based patient medical ecords                                                          | 
| System                       | Some activities are initiated by the system internally.                                                                                   | 



# Use Cases

надо проверить список сценариев, сделать приятное описание, и проставить ссылки на Акторов (проверить что они совпадают с таблицой выше)


| #    | Use Case                                | Short Description                                                                                                     | Actor                        | Requirement |
| ---- | --------------------------------------- | --------------------------------------------------------------------------------------------------------------------- | ---------------------------- | ----------- |
| UC01 | Login in system                         | User logs into the system.                                                                                            |            |             |
| UC02 | Register Medical staff in system        | Registers Medical Staff and Medical Professionals in system.                                                          |
| UC02 | Mapping Devices                         | Configure system by adding new devices and mappring them to "patiend bed" and Nurses                                  |
| UC03 | Register Patient in system              | Registers Patient and assign them to "bed" and to Doctor                                                              |
| UC04 | Collect vital sign                      | System collect vital signs from patient-monitoting devices.                                                           |  System, Patient-monitoring Device   |          |
| UC05 | Monitor patient vital status            | Nurse able to monitor all vital sign for                                                                              |                     |          |
| UC06 | Configure Thresholds                    | Configure thresholds for different types on vital sign (also interdepended signs)                                     |                     |          |
| UC07 | Recieve Alert notification              | Medical Staff recieve notificaion if any thresholds achieved                                                          |                     |          |
| UC08 | Generate vital sings stapshot           | Medical Professionals configure snapshot of data and data stored in MyMedicalData system                              |                     |          |
| UC09 | Analyse historical vital data           | Medical Professionals can view, filter vital sign history in frame of 24h                                             |                     |          |
| UC09 | Managing Hostpitals/MontorMe Instances  | StayHealthy techincal staff able to provision new Hostpital/MonitorMe instance                                        |                     |          |

