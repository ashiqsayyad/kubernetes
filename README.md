# kubernetes
Hands on K8s

# POD PLACEMENT
nodeName, nodeSelector, Node Affinity and Anti Affinity, Pod Affinity and Anti Affinity,Taints & Tolerations

# Running UBUNTU container

However, it’s not as simple as running the ubuntu image on its own. You need to make it actually do something or the container will just exit immediately. Fortunately this is easy enough… just make the container sleep for a long time!
#kubectl exec -it ubuntu -- /bin/bash >> after exec into container,you can run any ubuntu commands for example apt update && apt install curl -y