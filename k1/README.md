# Steps to Deploy


#### Create Application

Get the code

```
.
```

Create image:

```
docker build --tag k1:v1.5 .
```

Build Image GCP:
```
gcloud builds submit --tag gcr.io/kanjih-gcp/k1:v1.5
```

#### K8s Steps

Create Deployment

```
kubectl create deployment k1 --image=gcr.io/kanjih-gcp/k1:v1.5
```

Expose the Deployment

```
kubectl expose deployment k1 --type LoadBalancer --port 80 --target-port 8080

```

#### Inspect and view the application

*  Inspect the running Pods by using kubectl get pods
```
kubectl get pods
```

 *  Inspect the hello-server Service by using kubectl get service
```
kubectl get service k1

```