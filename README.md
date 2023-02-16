# frontfinance
This is the test task for devops

How can you restrict networking between pods in Kubernetes give an example should this mechanism be enabled separately ?
To restrict networking between pods in Kubernetes, you can use Kubernetes Network Policies. Network Policies allow you to define rules that determine which pods can communicate with each other, based on their labels.

Below steps defined - 

#STEP-1
Apply this Network Policy to your Kubernetes cluster:

kubectl apply -f restrict-traffic.yaml

#STEP-2
check if Network Policies are enabled in your cluster by running the following command:

kubectl api-versions | grep networking


#STEP-3
If you see networking.k8s.io/v1 or higher in the output, then Network Policies are enabled in your cluster. If you don't see this API version, then you may need to enable Network Policies separately, depending on your Kubernetes distribution.
