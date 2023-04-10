## Astronomer docs

#### Astronomer

- modern orchestration tool

- orchestrate your data into multiple gcp services.

-  airflow as service .in airflow ,workflow is represented as dags .


**Three environments**-*dev,preprod,prod*

 **dev** for developers --for testing

 **prepod**-customers,after compeleting poc they go to prod

Each and every customer will get a dedicated workspace.it is not shareable.

 workspace assigned to customer 1 cannot be seen by customer 2.

*--RBAC*

Inside workspace,we can create n number of deployments(creating namespace in GKE cluster). 

**Namespace** consists of

-  scheduler-scheduling the dags.dependencies also calculated

-  web server-the actual 

-  worker

They help to run the deployments healthy

Namespace running in gke is getting accessed to gcp services using service accounts

From gke it can access all gcp services from the respective project through service account.

**Types of executers**

 1. *local*-developer work in local

 2. *kubernetes*-whenever request is coming,it provisins the pod .once it is completed,it is destroying the pod. ON/OFF 
 
 3. *celery*-the pod is always on.once the signal is received from deployment.many loads are running.this is helpful(cost is high).

#### HOUSTON

 If you want to test before keeping it in the pipeline ,we have a playground for each env.

For dev 

          houston.astrodev.ford.com 

**Queries**-mutation,query

   1. class of mutation-create a workspace

   2. class of query-list deployments under a workspace

queries-graph ql format

authorization is provided by service acc with cisadmin access.

#### Alerts

 1. *deployment*-anything in deployment goes wrong(scheduler is not working,deployment is unhealthy)

 2. *platform*-anything goes wrong in the platform level(software installation is unhealthy,pods are not creating properly)

For each env,we have a config file.

  In the config file,under alert manager it needs to send alerts to emails and then webhook

  Whenever something goes wrong in the platform level,it will send a alert.

  From which address it has to come??astropp.ford.com to the bulk id

  Ticketing to us with appropriate priority-*high,crtical,low*

  For creating tickets integrated with team ---they will provide a webhook to us.

  Whenever there is an alert it will send those alerts to the webhook.team will collect and create an it connect ticket to us.

For each env,seperate prometheus and alert manager.

  - inactive-green colour

  - active-red 
  
prometheus will collect it and alert manager will send the alerts to webhook.

**Alert manager**

 Silences- when we upgrade our software,there might be lot of alerts telling that these pods are unhealthy.

 We have create a silence to stop those alerts from coming for a ceratin period of time.

 #### Astronomer UI

![astronomer UI](astro.png)

