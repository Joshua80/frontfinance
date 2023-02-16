#Task Blue/Green deployment strategy -

<span style="color:green">This text is blue</span>

What is the blue/green deployment strategy for k8 based on deployments service and ingress please describe how to switch versions ?
Ans - Blue/green deployment is a deployment strategy used in Kubernetes for releasing new versions of an application with zero downtime. In this deployment strategy, two identical environments or "deployments" of the application, called "blue" and "green", are maintained at the same time. Traffic is initially routed to the "blue" environment, while the "green" environment is updated with the new version of the application. Once the "green" environment has been successfully deployed and tested, traffic is switched over to it and the "blue" environment is decommissioned. This approach ensures that there is always a working version of the application available, even during the deployment process.

Below steps for Deployments, Services, and Ingress.

Deployment named my-app and a service named my-app-service, created two additional deployments and services for the blue and green environments.

+ STEP-1

The my-app-blue Deployment and my-app-blue-service Service are created with the my-app:blue image, while the my-app-green Deployment and my-app-green-service Service are created with the my-app:green image.

+ STEP-2

replicas for my-app-blue to 1 to ensure that at least one instance of the "blue" environment is running, while the my-app-green Deployment is initially set to 0 replicas to prevent traffic from being routed to it.


+ STEP-3

To switch traffic from the "blue" environment to the "green" environment, we can use an Ingress resource



+ STEP-4

Creating an Ingress resource with a my-app.example.com hostname and a / path. The my-app-blue-service Service is initially set as the backend for this Ingress, which means that traffic is initially routed to the "blue" environment.

To switch traffic to the "green" environment, we can update the Ingress resource 
