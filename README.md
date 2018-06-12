# Helm POC

Build a template to deploy microservices with envoy sidecar and its configuration

# Preconditions

* You need a working kubernetes cluster, for example minikube
* Helm installed in the cluster (by using helm install)

# Operations

To create the application nder the root directory execute

`helm install -f <microservice_values> -n <app_name> ./microservice-mesh`

where _microservice_values_ is the yaml configuration for a concrete microservice
(The root directory includes a _pet.yaml_ for demonstration purposes)

That will create all the resources (deployment, config-map and service)

To access the service just execute (assumming you are using a minikube cluster)

`minikube service <service_name>`

To verify correct execution, just add '/pets?petStoreId=2' to the open tab and it should show a json

To see existing helm deploys:

`helm ls`

To delete the installation execute:

`helm delete <helm_deploy_name>`

Consider that _helm_deploy_name_ is the name listed in the _helm ls_ command
