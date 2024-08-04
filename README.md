# kubernetes
Hands on K8s

# POD PLACEMENT
nodeName, nodeSelector, Node Affinity and Anti Affinity, Pod Affinity and Anti Affinity,Taints & Tolerations

# Running UBUNTU container

However, it’s not as simple as running the ubuntu image on its own. You need to make it actually do something or the container will just exit immediately. Fortunately this is easy enough… just make the container sleep for a long time!
#kubectl exec -it ubuntu -- /bin/bash >> after exec into container,you can run any ubuntu commands for example apt update && apt install curl -y

# K8s CNI vs Kube-Proxy

# Notes on demo_init-container-nginx.yaml
initContainers - container which will run and complete before main container starts
  It will run busybox image. 
  It will download the file https://raw.githubusercontent.com/kubernetes/website/main/content/en/examples/application/nginx-app.yaml and copy to folder /usr/share/nginx/html/index.html which is locally mounted using volumeMounts shared-data

containers - Main Container 
   It will run nginx:latest image.Nginx displays the file index.html which is located at /usr/share/nginx/html/index.html which is updated by initConainers
   To run the main container from your development machine, use port forward  using below command
   
   kubectl port-forward svc/myservice 8080:80
   Now from local machine , open URL http://127.0.0.1:8080/  which will show contents of link https://raw.githubusercontent.com/kubernetes/website/main/content/en/examples/application/nginx-app.yaml
