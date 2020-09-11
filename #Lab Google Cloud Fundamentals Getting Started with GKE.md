#Lab: Google Cloud Fundamentals: Getting Started with GKE

##Objectives:

In this lab, you learn how to perform the following tasks:

- Provision a Kubernetes cluster using Kubernetes Engine.

- Deploy and manage Docker containers using `kubectl`.

  

Step 1:

Place the zone in an environment variable called MY_ZONE.

> export MY_ZONE=us-central1-a

Start a Kubernetes cluster managed by Kubernetes Engine.

> gcloud container clusters create webfrontend --zone $us-central1-a --num-nodes 2

Validate the version of Kubernetes:

> kubectl version

Step 2:

Run and Deploy a container

From Cloud Shell prompt, launch a single instance of the nginx container:

> kubectl create deploy nginx --image=nginx:1.17.10

View the pod running the nginx container:

> kubectl get pods

Expose the pod to the internet

> kubectl expose deployment nginx --port 80 --type LoadBalancer

View the new service

> kubectl get services

Scale up the number of pods running on your service:

> kubectl scale deployment nginx --replicas 3

Confirm that Kubernetes has updated the number of pods:

> kubectl get pods

Confirm that your IP address has not changed

> kubectl get services

Step 3:

Return to the web browser tab in which you viewed your cluster's external IP address. Refresh the page to confirm that the nginx web server is still responding.