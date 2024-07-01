Based on hashicorp.com eks tutorial at https://developer.hashicorp.com/terraform/tutorials/kubernetes/eks
Then deploying my go echo-server container at tcanning/echo-server based on the tutorial at https://clouddevs.com/go/applications-on-kubernetes/

To deploy I ran the following commands:
kubectl apply -f pod.yaml
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
kubectl get svc echo-server-service :To get the external IP address of the service
kubectl scale deployment my-go-app --replicas=2 :To scale the deployment to 2 replicas

Then deleted the kubernetes resources and used helm to deploy the service
Created a helm chart with the command create echo-server
Then edited the values.yaml, service.yaml and deployment.yaml files
Then deployed the helm chart with the command helm install echo-server-release echo-helm-service/

Then added the helm chart to the main.tf