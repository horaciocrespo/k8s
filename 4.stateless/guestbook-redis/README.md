# Source code

* https://cloud.google.com/kubernetes-engine/docs/tutorials/guestbook
* https://github.com/GoogleCloudPlatform/kubernetes-engine-samples

# Deploy

```
kubectl apply -f redis-leader-deployment.yml
kubectl apply -f redis-leader-service.yml

kubectl apply -f redis-follower-deployment.yml
kubectl apply -f redis-follower-service.yml

kubectl apply -f frontend-deployment.yml
kubectl apply -f frontend-service.yml
```

# Visiting the guestbook website

To access the guestbook Service, find the external IP of the Service that you set up by running the command:

`kubectl get service frontend`

```
NAME       CLUSTER-IP      EXTERNAL-IP        PORT(S)        AGE
frontend   10.51.242.136   109.197.92.229     80:32372/TCP   1m
```

Copy the IP address from the EXTERNAL-IP column, and load the page in your browser:

# Visiting the guestbook website (Locally)

Go to localhost:30006

# Scaling up the web frontend

Scale up the number of your frontend Pods to five by running:

```
kubectl scale deployment frontend --replicas=5
```

# Clean up
