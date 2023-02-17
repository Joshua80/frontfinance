#k8 deployment strategy which contains an azure function.

Make a k8 deployment strategy which contains an azure function in python with source code which puts a message to azure storage queue every minute then make another function that  should load a message from a queue and run a prepared container service to print "Hello world" 

#Example:
Two Azure Functions, one that puts a message to an Azure Storage Queue every minute, and another that loads a message from the queue and runs a container service that prints "Hello world".

#Step:1 -
Azure Function for putting messages to the queue.
Azure Function in Python that puts a message to the Azure Storage Queue every minute.using the Azure Functions Core Tools to create and deploy this function. Above the source code for the function.
Function retrieves the connection string and queue name from environment variables, creates a QueueClient instance, and sends a message to the queue with the current timestamp.

#Step:2 -
Azure Function for running the container service
Azure Function in Python that loads a message from the queue and runs a container service that prints "Hello world". Above the source.prints code for the function.
This function retrieves the message from the queue, retrieves the container group details and credentials from environment variables, and restarts the container group. We'll set up a queue trigger to run this function whenever a message is added to the queue.

#Step:3 -
Kubernetes deployment -a Kubernetes deployment that includes these two functions.Created two separate deployment files, one for each function.
