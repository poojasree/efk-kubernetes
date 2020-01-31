# EFK Installation and set up in K8s

Centralized logging is an essential part of your system regardless if it's a micro-services or a monolith platform. It helps your development team quickly observe, search and aggregate their application logs through a web browser with a few button click.
This POC will give an overview on how you can quickly aggregate container logs from your Kubernetes pods and view them from a Kibana dashboard

# You need a few things.
1.	An existing Kubernetes Cluster.
2.	kubectl binary locally installed

# Getting a Kubernetes Cluster
Install Google Kubernetes Engine in GCP and connect through cloud shell interface

Create a namespace logging

$ kubectl create namespace logging

# Deploying an Elasticsearch Cluster with Helm
Add elasticsearch helm repository

$ helm repo add elastic https://Helm.elastic.co

Install the chart

$ helm install elasticsearch elastic/elasticsearch -f ./values.yaml -n logging

Check the pod status

$ kubectl get pods -n logging

