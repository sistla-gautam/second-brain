## Introduction
- The service provides an application that will allow the user to create new interactive forms that can be deployed and accessed by other users
- The service also provides ability to read and write values from APIs and datasources

### Service Specification
Current deployment:
- No of pods running
- Resource requests and limits:
 
## Impact
If the service is down, Interactive forms will not be available for dependent applications

## Release Notes

| Release  | Factsheet version | Featues | Deprecation Notices |
| -------- | ----------------- | ------- | ------------------- |
| R5.03.xx | vxx               |         | None                |

## Recoverability
The time taken for the pod to restart is 120s

## Security
- Interactive forms pods not exposed using any ports for external use

## Data Integrity
#### Validation
- All inputs undergo validation to prevent any types of errors or crashes

## Availability
Rolling updates are available for the kubernetes deployment.

Availability calculations based on the probability of failure and time to recover, excluding the time taken to acknowledge or any infra-related setup time, are as follows:

Time taken for all outage = ((1\*30) + (1\*30) ) = 60 minutes

Time taken for downtime identification = 2\*60 = 120 minutes

Availability = (43200 - 180)/43200 = **99.5%**

|                  |                               |                             |
| ---------------- | ----------------------------- | --------------------------- |
| **Failure type** | **Time to repair (In mins.)** | **Frequency (Times/Month)** |

|                  |                               |                             |
| ---------------- | ----------------------------- | --------------------------- |
| **Failure type** | **Time to repair (In mins.)** | **Frequency (Times/Month)** |

|   |   |   |
|---|---|---|
|**Failure type**|**Time to repair (In mins.)**|**Frequency (Times/Month)**|
|Pod failure|30|1|
|Misconfiguration and leading to pod crash|30|1*|

(*: _Assuming 1 new pipeline is created in a month_.)

#### Capacity and scalability
The service is horizontally scalable. However, the scaling is manual.