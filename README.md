Module 1: 

In /k8s folder you can find kubernetes manifests for microservices-intro project.
You can use them to deploy the project to your kubernetes cluster.

to build docker images for microservices-intro project you can use the following command:

```
docker build -t songs-image:local -f songs-service/Dockerfile .
docker build -t resources-image:local -f resources-service/Dockerfile .
```

in secret.yaml  fill the DB creds.



Manifest files are ordered by the number in the file name, so you can deploy them in order.
For  deploying the project to your kubernetes cluster you can use the following command:

```
kubectl apply -f ./k8s/
``` 
or you can deploy each service separately:

```
kubectl apply -f ./k8s/00-namespace.yaml
kubectl apply -f ./k8s/01-configmap.yaml

etc...
``` 

then check the pods status with the following command:

```
kubectl get pods -n k8s-application
```


