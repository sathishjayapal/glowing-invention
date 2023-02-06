# glowing-invention
Cheatsheet commands
### Docker commands 1x1- 
- docker run alpine sleep 5 -> runs an image and exits after 5 seconds
- docker run ubuntu bash -> just runs the bash
- docker run ubuntu -> it bash - runs the bash command in with an interactive prompt
- docker ps -a -> lists all container with a detailed information includes the running and exited
- docker ps -> lists all the images
- docker pull alpine -> pulls the image from docker-hub and imported
- docker run -it openjdk bash -> Download openjdk run bash
- docker run -it node bash -> Download node and run bash

### Docker save  commands- 
- docker save alpine -o alpine.zip -> creates the alpine.zip from the alpine image
- docker stop b1f3bfb5db9d -> stops the image b1f3bfb5db9d
- docker kill b1f3bfb5db9d -> Kills the image b1f3bfb5db9d
- docker run --name my-java -it openjdk bash -> runs the container with name "my-java"
- docker kill my-java -> kills the container by name my-java
- docker rm 769870c76a87 -> removes the container from the local docker repo
- docker start b1f3bfb5db9d -> starts the container with image docker start b1f3bfb5db9d

### Docker commands exec commands-
- docker exec b1f3bfb5db9d java --version -> When there is a running image then u can call the exec command
- docker run --rm -it

### Docker commands MySql Runs-
- docker run --name my-mysql -e MYSQL_ROOT_PASSWORD=pass -d mysql --> Download and running sql
- docker exec -it my-mysql mysql -p    --> interactively interact with the container
- docker run --name my-mysql-2 -e MYSQL_ROOT_PASSWORD=pass -v ${PWD}:/var/lib/mysql -d mysql -> Volume mount 

### Docker commands volumes-
- docker run -rm -it -v ${PWD}:/javacode openjdk sh -> Run with volume mount and copy the java file in current directory to /javacode in container and call shell command
- docker volume ls -> lists all the docker volume
- docker volume create new-vol -> Creates a docker volume called new-vol
- docker volume inspect new-vol -> inspects the volume new-vol
- docker run -it --rm -v new-vol:/vol alpine sh -> attaches the new-vol to the container 
- docker run -it --rm -v new-vol:/sats ubuntu bash -> attaches to the ubuntu world now but any files in the new-vol is going to be carried over.
- docker volume rm new-vol -> removes the volume
- Docker desktop gives a UI view of the volumes attached. See the data tab in the volume then we can see the files. 

### Docker commands ports-
- docker run -it -p 8080:80 nginx
K8s Information

### install hyperhit and minikube
`brew update`
`brew install hyperkit`
`brew install minikube`
`kubectl`
`minikube`

### create minikube cluster
`minikube start --vm-driver=hyperkit`

`kubectl get nodes`

`minikube status`

`kubectl version`

### delete cluster and restart in debug mode
`minikube delete`

`minikube start --vm-driver=hyperkit --v=7 --alsologtostderr`

`minikube status`

### kubectl commands
`kubectl get nodes`

`kubectl get pod`

`kubectl get services`

`kubectl create deployment nginx-depl --image=nginx`

`kubectl get deployment`

`kubectl get replicaset`

`kubectl edit deployment nginx-depl`

### debugging
`kubectl logs {pod-name}`

`kubectl exec -it {pod-name} -- bin/bash`

### create mongo deployment
`kubectl create deployment mongo-depl --image=mongo`

`kubectl logs mongo-depl-{pod-name}`

`kubectl describe pod mongo-depl-{pod-name}`

### delete deplyoment
`kubectl delete deployment mongo-depl`

`kubectl delete deployment nginx-depl`

### create or edit config file
`vim nginx-deployment.yaml`

`kubectl apply -f nginx-deployment.yaml`

`kubectl get pod`

`kubectl get deployment`

### delete with config
`kubectl delete -f nginx-deployment.yaml`

#Metrics

`kubectl top` The kubectl top command returns current CPU and memory usage for a cluster’s pods or nodes, or for a particular pod or node if specified.



