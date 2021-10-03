# Steps to Deploy


#### Create Application

Get the code

```
.
```

Create image:

```
docker build --tag k2:v1.0 .
```

Build Image GCP:
```
gcloud builds submit --tag gcr.io/kanjih-gcp/k2:v1.0
```

Run local:
```
 docker run --publish 80:8080 k2:v1.0
```

#### K8s Steps

Create Deployment

```
kubectl create deployment k2 --image=gcr.io/kanjih-gcp/k2:v1.0
```

Expose the Deployment

```
kubectl expose deployment k2 --type LoadBalancer --port 80 --target-port 8080

```

#### Inspect and view the application

*  Inspect the running Pods by using kubectl get pods
```
kubectl get pods
```

 *  Inspect the hello-server Service by using kubectl get service
```
kubectl get service k2

```