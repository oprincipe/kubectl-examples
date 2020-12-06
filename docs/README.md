# Kubernates:

## CREATE NGINX DEPLOYMENT
> kubectl run my-nginx --image nginx (creates a ReplicaSet, which creates a Pod)

> kubectl create deployment nginx --image nginx (Creating a Deployment in 1.18)

> kubectl get pods (get all)

> kubectl delete deployment my-nginx

## CREATE APACHE DEPLOYMENT
> kubectl create deployment my-apache --image httpd

## SCALE APACHE TO 2 REPLICA
> kubectl scale deployment my-apache --replicas 2

## GET CONTAINER LOGS
> kubectl logs deployment/my-apache

> kubectl logs deployment/my-apache --follow --tail 1 (to follow and tail the logs)

## GET MULTIPLE PODS LOGS _(up to 5 pods together)_
> kubectl logs -l run=my-apache

## DESCRIBE POD
> kubectl describe pod/my-apache-7b68fdd849-xkc65

## WATCHING PODS
> kubectl get pods -w

## EXPOSING CONTAINERS
###### kubectl expose -> create a service for existing pods
###### A service is a stable address for pod(s)
###### if we want to connect pod(s), we need a service

## SERVICES
CoreDNS allow us to resolve services by name
There are different types of services: @SEE services.txt

## Delete all services and deployments
> kubectl delete service/httpenv

> kubectl delete service/httpenv-np

> kubectl delete service/httpenv-lb

> kubectl delete deployment/httpenv


## GENERATORS
_Run, Create and Expose Generators_
###### these commands use helpers templates called "generators"
###### Every resource in Kubernetes has a specification or "spec"
> kubectl create deployment test --image nginx --dry-run -o yaml

> kubectl create job test --image nginx --dry-run -o yaml (something you want to run once)

> kubectl expose deployment/test --port 80 --dry-run -o yaml (the deployment should exists)


## APPLY A YAML FILE/DIRECTORY/URL
###### Avoid, if possible, to use kubectl create, kubectl replace, kubectl edit
###### cause they're not that good to create your infrastructure in production

> kubectl apply -f filename.yml

> kubectl apply -f myfiles/

> kubectl apply -f https://yourdomain.com/pod.yml -> not recommended

