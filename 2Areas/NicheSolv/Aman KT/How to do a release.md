### most applications
- create a new branch for every release
- any changes to the `env.local` should also be made into the `editor-configmap.yaml`
- do the merge into master only when the sonarqube is properly passed and all the test cases are done
> keep the QA handover document in confluence as reference to what is to be done

#### Things to be completed
Can be found in the QA handover document
- postman collection
- functional specification
- service factsheet
- TI test cases (some spreadsheet - Sushma)
- TI bug fix (Sushma)
- TL bug fix (Sushma)
- github actions for CI/CD (dev deployment)
- sonarqube evidence (screenshots - just maintain the latest)
	- make sure the sonarqube evidence is from the release branch
	- the sonarqube can be done on the release/feature branch, but for final we need to use the master branch
- OSS license spreadsheet file
	- send out an email to some guys (ask Santosh YTI) saying the different records that are updated in the spreadsheet
- vulnerability report
	- docker scan reports. make sure that this is done before pushing the release branch to the master
	- the scan can be done on the release branch, but the reports should be done with the master branch
- deployment document
	- confluence docs will be updated by YTI team, update the links of the same
- deployement automation script
	- skip unless something very new
- OPA
	- Can sit with Santosh on what needs to be released and how
- CORS
	- mention no changes
- Operations
	- rarely changed
- wikiJS (Sushma)
- security review
	- combination of some stuff
	- make sure to update the stuff from OSS here also
- Apps onboarding
	- skip
- User onboarding
	- skip
- 
- 
- 
- release notes
	- just point to the confluence docs
- Guacamole notes
	- confluence files for guacamole
- 36 will be Rollback which should be added in the next release

### things that will happen in a rollback
- roll back needs to be implemented
- roll back has to be tested 
- example scenario:
	1. Upgrade from **R4.02** to **R5.01.01** -> QA validates
	2. Rollback from **R5.01.01** to **R4.02** -> QA validates
	3. Re-Upgrade from **R4.02** to **R5.01.01** -> QA validates