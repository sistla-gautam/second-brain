### problem statement
- no natural language processing for knowing the movies

### solution
###### steps
- gather the data
- create the vectors
- build the chatgpt and deploy it
---
## neo 4j
###### graphs
- each node is a element
	- contains JSON values that holds values
- nodes connected using relationships
	- contains JSON values that holds values
- each relation is the cosine similarity between the different nodes

### querying
- cypher
	- read querying
	- write querying

> check this out - [aura db](https://console.neo4j.io/?ref=pricing-page&mpp=4bfb2414ab973c741b6f067bf06d5575&mpid=%24device%3A196286bdcaa31f-024c2d9b46f65e-26011c51-384000-196286bdcaa320)

==only problem with graph database is scaling==

**the main difference between databases and graph is the relationship between the nodes**
the nodes contains context, but database does not necessarily contain this

### different places where to use graphs
- use it for relations
- not good for high storage data
- what if we want both?
	- relations handled by graph
	- store additional data in mongo/postgres
	- call the data whenever required for additional context


