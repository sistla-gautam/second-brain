types of data
-  structured
- unstructured
- semi structured

three different V of data
- volume
- velocity
- variety
- also has veracity

data warehouses vs data lakes
- warehouses
	- structured format storage
	- read heavy format
	- star or snow flake format storage
	- data undergoes ETL process
	- amazon redshift
- lake
	- large repo of all types of data
	- structured, semi structured and unstructured data - holds in its native format
	- no pre processing
	- supports real time, batch and stream processing
	- data undergoes ELT process or just store
	- amazon s3 as a data lake
- data lakehouses
	- hybrid between lakes and warehouses
	- structured and unstructured
	- schema on read and schema on write

data mesh
- decentralized approach to storage of data
- every team will store and govern their own data

ETL pipelines
- extract
	- when
	- how often
	- can be from API, databases, other applications
	- duplicates, data integrity
- transform
	- computing values
	- changing values
	- changing formats, string manipulation
	- encoding decoding values
- loading
	- can be done in batches or realtime
	- ensure data integrity
- amazon 

sources
- jdbc
	- platform independent
	- language dependent
- odbd
	- platform dependent (drivers)
	- language independent
- raw logs
- APIs
- streams

common data formats
- CSVs
	- small to medium datasets
	- common
	- human readable and ediitable
- JSON
- Avro
  encoded binary type of data
	- stores both data and schema
	- appropriate for large databases
	- encoded
- parquet
	- columnar type of data
	- used primarily for data analysis
	- efficient encoding and compression
- 
