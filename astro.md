## Astronomer docs

#### Astronomer

- modern orchestration tool

- orchestrate your data into multiple gcp services.

-  airflow as service .in airflow ,workflow is represented as dags .


Three environments-*dev,preprod,prod*

 **dev** for developers --for testing

 **prepod**-customers,after compeleting poc they go to prod

each and every customer will get a dedicated workspace.it is not shareable.

 workspace assigned to customer 1 cannot be seen by customer 2.

**--RBAC**

Inside workspace,we can create n number of deployments(creating namespace in GKE cluster). 

Namespace consists of

-  scheduler-scheduling the dags.dependencies also calculated

-  web server-the actual 

-  worker

They help to run the deployments healthy

Namespace running in gke is getting accessed to gcp services using service accounts

From gke it can access all gcp services from the respective project through service account.

**Types of executers**

 1. *local*-developer work in local

 2. *kubernetes*-whenever request is coming,it provisins the pod .once it is completed,it is destroying the pod. ON/OFF 
 
 3. *celery*-the pod is always on.once the signal is received from deployment.many loads are running.this is helpful(cost is high)