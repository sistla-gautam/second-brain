The Operations team must take the following points into account while working with the Visualization Configuration Tool.
- Observability
	- Monitoring Service Components
	- Metrics
	- Service probe
	- Logs


## Monitoring service components

| Category | Components                | Type            |
| -------- | ------------------------- | --------------- |
| Service  | appsmith-vs               | virtual service |
| Service  | appsmith-0                | k8 pods         |
| Service  | appsmith-redis-master-0   | k8 pods         |
| Service  | appsmith-redis-replicas-0 | ks pods         |

##### The stability of the service is defined by 
- the appsmith-0 pod should be up and running without any errors in the pods
- the mongodb should be up and running without any type of errors in the mongodb
- SAPCDC login should be working fine without any type of issue