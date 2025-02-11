1. is it integrated with pipeline
	1. no
2. test helm based appsmith?
	1. Helm deployment (manual deployment) is tested. But it points to mongo and redis that is part of the helm which appsmith have provided
3. open issues in existing deployment?
	1. Ci cd for new docker image v creation is not setup. Basic Initial setup was done in Jenkins also GitHub actions but there are issue. GitHub actions server in ydx repo is not capable to build the app because of resource issue. Jenkins also had same issues. Need a dedicated GitHub or Jenkins server for this. Preferred will be GitHub because we can use the workflow that was there in my appsmith repo
4. single tenant/multi tenant?
	1. at the time of discussion, single tenant
5. can we make use of existing mongo?
	1. need to test
6. existing helm chart available?
	1. Yes existing helm chart is available. Its provided by appsmith so you can just search for appsmith kubernetes helm on Google and make required changes