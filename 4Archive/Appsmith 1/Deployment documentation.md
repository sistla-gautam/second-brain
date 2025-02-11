Appsmith deployment details

### Integration with pipeline
Has not been integrated with pipeline and might not require integration with pipeline

### Helm based Appsmith deployment
Appsmith provides us a with a standard helm for deployment, but this helm points to a separate mongo instance. The plan is to use existing mongo service. needs to test further on the same

### existing issues in deployment
the CICD does not have enough computation power to do the docker image build. a workaround jenkins or any other alternative is required to build the docker image of Appsmith

### existing mongo for appsmith
Appsmith does provide support for the same. need to test

### existing helm chart available?
appsmith provides one for the open source version (community edition). this is the one which we have used for the initial deployment.

The documentation for the same can be found [here](https://docs.appsmith.com/getting-started/setup/installation-guides/kubernetes)