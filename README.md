# Tasks List Application 

This project is to understand how 3 tier application works on Kubernetes. also, to get insights on each k8s resource, concept and traffic flow. this architecture covers high availability, scalability & security.

# Application Architecture Background


The application we are going to deploy has front end implemented with Angular Framework, and back end implemented with Spring Boot Framework, we will build executables with build tools (Angular CLI and Maven in this case) and we are using backend database is MySql
This application is simple Tasks List/Todo List creator, you will be accessing the frontend to create the list where backend will save the record to database and also helps to get the records from database.

	Database (MySQL server)   * Using stateful set to Run a Replicated Stateful Application 
	Back end (Java Spring Boot application) * using Load balancer with HTTPS listener
	Front end (Angular app) * Using Ingress Controller, Ingress and Application Load Balancer and External DNS

## Kubernetes Background and Dependencies
1.	We will deploy all of these components on a Kubernetes cluster. 
2.	We will configure the cluster by creating Kubernetes objects. These Kubernetes objects will contain the desired state of our deployment. Once these objects are persisted into the cluster state store, the internal architecture of Kubernetes will take necessary steps to ensure that the abstract state in the cluster state store is the same as the physical state of the cluster.
3.	We will use kubectl to create the objects.
4.	We will use the declarative approach in this example. For each object, we will first prepare a manifest file, a yaml file containing all the information related to the object. Then we will execute the kubectl command, kubectl apply -f <FILE_NAME>to persist the object in the cluster state store.


## Manual Deployment Steps (deploy each component and playaround before going to next step) 
	Step 1. Containerize the application
	Step 2. Database pre-requisite configuration setup
	Step 3. Configure PVC, SQL Service, and statefulset for database
	Step 4. Configure service and deployment for backend
	Step 5. Front-end configuration setup 
	Step 6. Configure service and deployment for frontend
	Step 7. Setting up ExternalDNS for Services on AWS
	Step 8. Configure Horizontal Pod Autoscaler for frontend and backend deployments for high availability
	Step 9. Deploy ClusterAutoScaler
	Step 10. Deploy PodSecurityPolicy
	Step 11. Apply Network Policies
	Step 12. Test the application





## Author

Kiran Kaukuntla
