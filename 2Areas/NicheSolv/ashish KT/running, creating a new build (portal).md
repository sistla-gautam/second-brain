- change the token in the .env with the following
	- prod (old) - `sp=r&st=2023-11-21T10:40:13Z&se=2024-11-19T18:40:13Z&spr=https&sv=2022-11-02&sr=c&sig=s9vwH%2Fn27ruZpX1V6mAW9HraZ5R1K2paVkS3QElNMDU%3D`
	- prod (new) - `sv=2022-11-02&ss=bfqt&srt=sco&sp=rlapitfx&se=2026-08-29T21:16:11Z&st=2024-08-29T13:16:11Z&spr=https&sig=eewi0%2BudIxIGRa%2FhU06RGSpCHkNYYRpwlGI4J75%2FWV4%3D`
	- dev - `sp=racwdl&st=2024-02-28T05:59:32Z&se=2025-02-27T13:59:32Z&spr=https&sv=2022-11-02&sr=c&sig=Mv7esnK0vA%2B%2FoTFJ8tDVPd7PFciANFwFGCdPWLn8doE%3D`
	- only after replacing will the build or running work
- remember to replace it back to `TOKEN` when pushing the code to GitHub
#### changing from prod to dev
- in `.env`, change the `xxxx` in `ydxmasterstoragexxxx` to the given values
	- prod(old) - `59839`
	- dev - `6019`
- if required, change the library to the required number in the `REACT_APP_LIBRARY` to the latest value

#### creating a new build
- change the `REACT_APP_BASE_PATH` based on the deployed URL - best to ask Aman for this value
- make sure to revert from dev changes to prod changes then build the application
- [[KBC portal]] - refer this to create a new build
- this will create a new .zip file - this is the new build
	- upload this to the portal for testing 
	- post testing - pass it to Aman for deployment