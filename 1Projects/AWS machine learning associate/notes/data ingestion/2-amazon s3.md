- infinitely scalable storage
- pretty similar to cloudflare bucket
- this is a bucket type of storage.

### use cases
- backups
- archives
- media storage
- static website
- media hosting
- data lakes, big data analytics


### buckets
- basically directories
	- not true directories
	- globally unique name (across regions, across accounts)
	- buckets are created in a global level
	- naming convention
		- 3 - 63
		- not an IP
		- no uppercase, no underscore
		- must start with lowercase or number
		- have specific suffixes and preixes that are not allowed

### files
-  names are the full name
	- path + name of the file
- all the files have unique keys (the path + the file name)
- the keys are the contents of the file
	- can hold upto 5TB
	- if the file is above 5gb -> multi part upload

### file sharing
- the files can be setup to not be accessible to the general public
- this will give us 2 types of URLs that can be used
	- URls that are public (these will not be accessible to the people without proper permission) 
	- presigned URL that will contain the proper credential that will allow access to the URL

### security
- user based
	- based on the IAM policy
- resource based
	- bucket wide policies
	- object wide access control
		- bucket access control

when can a user access an S3
- if the IAM allows it
- resource policy allows it
- no explicit deny

### bucket policy
- JSON structure
- has the following fields
	- Effect - what should this rule do (Allow, deny)
	- Principal - who is this for
	- Action - what is the rule
	- Resource - what is the resource this is governing
![[Pasted image 20250517173610.png]]

- s3 has a default setting to stop from public access
- this can be set at a bucket level
	- additionally, if you want all of the buckets to not be accessible, this can also be set in the account level
- 