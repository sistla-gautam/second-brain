
# Dev deployment
 done using github action + manual changes
 - only deployment can be done with github actions
 - rest everything is manual changes
 - when doing manual changes, we need to also change in the code itself
	 - we do it so that we can keep track of the changes
	 - if we dont, the next time we do a code push, we will have the values overwritten by the new ones
## file and data service deployment

> file and data service is the first thing to get deployed
> this is dependent on minio and azure
###### minio changes
- for creating the required folders/ buckets, it can be done from the login screen side itself
> ==do not do the same for test side. always use pipelines==

*Common problems*
- users usually will not be created once the minio is upgraded
###### azure changes
- usual changes will be changes in the files
- files include template jsons and unit conversion changes
---
# Release
#### pipeline changes
#### documentation
---
# Appdev env deployment
---
# Mini env deployment