# ingress-hw
creating web app for spring-music image

# prequests:
docker
kubernetes 
ingress
minikube

# steps:

1. create a new deployment with the name spring-music by running the command line in the cmd:
kubectl create deployment spring-music --image=yanivomc/spring-music:latest

2.verify it's working with the command line:
kubectl get deployments

3.expose the deployment to get access to the the service from outside the Kubernetes virtual network:
kubectl expose deployment spring-music --port=8090 --target-port=8080

4.install the nginx ingress-controller in your cluster to access the app with your desired address:
minikube addons enable ingress

5. clone this project to get the ingress.yaml file:

6. create the Ingress in your cluster:
kubectl create -f ingress.yaml

7. now run your web app using this commandline:
curl -kL  http://127.0.0.1/music

thats it!

