# Decomposed Requirements

Requirements decomposition for linking.

## Functional requirements

[REQ.F.1](#REQ.F.1) Collect data from monitoring devices. See Device list.
> ...reads data from eight different patient-monitoring equipment vital sign input sources..

#System:MonitorMe:

[REQ.F.2](#REQ.F.2) Visualize data from monitoring devices per patient according to the predefined rules within particular Nurse station
> It then sends the data to a consolidated monitoring screen…

[REQ.F.3](#REQ.F.3) Monitoring data should be available during last 24 hours for the review
>"For each vital sign, MonitorMe must record and store the past 24 hours of all vital sign readings. A medical
professional can review this history, filtering on time range as well as vital sign."

**Actor: [Medical professionals](./03_Actors.md#Medical-professionals)**

[REQ.F.4](#REQ.F.4) Send alert in case of any vital sign value is out of regular range
> In addition to recording raw monitoring data, the MonitorMe software must also analyze each patient’s vital signs and alert a medical professional if it detects an issue (e.g., decrease in oxygen level) or reaches a preset threshold (e.g., temperature has reached 104 degrees F).

[REQ.F.5](#REQ.F.5) Regular range value (alert thersholds) depends on patient sleep state
> Some trend and threshold analysis is dependent on whether the patient is awake or asleep

[REQ.F.6](#REQ.F.6) Alerts received on mobile app and displayed on monitoring screen as well  
> Medical professionals receive alert push notifications of a potential problem based on raw data analysis to a
StayHeathy mobile app on their smart phone as well as the consolidated monitoring screen in each nurses
station.

**Actor: [Medical professionals](./03_Actors.md#Medical-professionals)**

[REQ.F.7](#REQ.F.7) Generate holistic snapshots from a patients consolidated vital signs at any time
> Medical staff can generate holistic snapshots from a patients consolidated vital signs at any time

**Actor: [Medical staff](./03_Actors.md#Medical-staff)**

[REQ.F.8](#REQ.F.8) Provide metrics collected from monitoring devices for further analysis
>...comprehensive data analytics platform that is used for hospital trend and performance analytics—alert response times, patient health problem analytics, patient recovery analysis…

[REQ.F.9](#REQ.F.9) Store patient health data
> MyMedicalData is a comprehensive cloud-based patient medical records system used by doctors, nurses, and other heath professionals to record and track a patients heath records with guaranteed partitioning between patient records.

#System:MyMedicalID:
**Actor: [Medical professionals](./03_Actors.md#Medical-professionals)**

[REQ.F.10](#REQ.F.10) Track patient health data

[REQ.F.11](#REQ.F.11) Store MonotorMe snapshot
> Medical staff can then upload the patient snapshot to MyMedicalData

#System:MyMedicalID:<br/>
**Actor: [Medical staff](./03_Actors.md#Medical-staff)**

[REQ.F.12](#REQ.F.12) Provide hospital trend
> MonitorThem a comprehensive data analytics platform that is used for hospital trend and performance
analytics—alert response times, patient health problem analytics, patient recovery analysis, and so on.

#System:MonitorThem:
**Actor: [Medical professionals](./03_Actors.md#Medical-professionals)**

[REQ.F.13](#REQ.F.13) Provide performance analztics

[REQ.F.14](#REQ.F.14) Provide alerts of responce time

[REQ.F.15](#REQ.F.15) Provide health problem analitics per patient

[REQ.F.16](#REQ.F.16) Provide health problem analitics per patient

[REQ.F.17](#REQ.F.17) Provide patient recovery analysis

[REQ.F.18](#REQ.F.18) Receive data collected from monitoring devices for further analysis
>...comprehensive data analytics platform that is used for hospital trend and performance analytics—alert response times, patient health problem analytics, patient recovery analysis…

[REQ.F.19](#REQ.F.19) Device data to be dicplayed on monitoring screen consolidated per patient.

[REQ.F.20](#REQ.F.20) Each patient data set displyed during 5 second period.

[REQ.F.21](#REQ.F.21) Monitoring data displayed in cycles.

[REQ.F.22](#REQ.F.22) Cysle size equal to the number of monitored patients per nurse station.

## Non-functional requirements

### Performance

[REQ.N.1](#REQ.N.1) Monitoring device data should be available for visualisation or alerting within less than 1 second
> "It then sends the data to a consolidated monitoring screen (per nurses station)
with an average response time of 1 second or less. "

[REQ.N.2](#REQ.N.2) Each nerse station should handle monitoring data fro up to 20 patients
> There is a maximum of 20 patients per nurses station.

[REQ.N.3](#REQ.N.3) Maximum number of patients per physical MonitorMe instance: 500
> Maximum number of patients per physical MonitorMe instance: 500

### Robustness/Fault tolerance

[REQ.N.4](#REQ.N.4) System should display monitoring data withregardless on any particular device availability.
> If any of vital sign device (or software) fails, MonitorMe must still function for other vital sign monitoring (monitor, record, analyze, and alert).

### Scalability

[REQ.N.5](#REQ.N.5) New vital sign sources (monitoring devices) should be easily added/configured by Medical staff.
> StayHealthy, Inc. is looking towards adding more vital sign monitoring devices for MonitorMe in the future.

### Reliability

[REQ.N.6](#REQ.N.6) Monitoring data should not be corrupted by the system during processing and should have precise cohesion to the coupled data managed by other system.
> Vital sign data analyzed and recorded through MonitorMe must be as accurate as possible. After all, human
lives are at stake.

### Extencibility

[REQ.N.7](#REQ.N.7) New pieces of functionality should be easily added.
> As this is a new line of business for StayHealthy, they expect a lot of change as they learn more about this
new market.

### Security/Provacy

[REQ.N.8](#REQ.N.8) Patient related data should not be available for the audience which it is not intended to.
> StayHealthy, Inc. has always taken patient confidentially seriously. MonitorMe should be no exception to this rule. While patient monitoring data must be secure, MonitorMe does not have to meet any government regulatory requirements (e.g., HIPPA).
