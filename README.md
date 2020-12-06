# Kubernetes examples
#### Imperative commands can be seen on docs directory

#Kubectl with yaml files
- Each file contains one or more manifests
- Each manifest describes an API object (deployment, job, secret)
- Each manifest needs four parts (root key:values in the file)

### _Examples into the examples folder_

Yaml file has the following sections

- `apiVersion:`
- `kind:`
  we can get a list of resources the cluster supports with
  > kubectl api-resources
  
    _You can find the same name but with **different APIGROUP** ex: deployments. 
  It's important to see which api should be used or to check what has been deprecated_
  > kubectl api-versions
  
- `metadata:`  only name is required
  
- `spec:` where all the action is at!
  - > kubectl explain services --recursive (this command will show all the possible specs available on kube
  - > kubectl explain services.spec (give you documentation of the first spec level)
  - you can go deeper with services.spec.A_SPECIFIC_TYPE. For example: kubectl explain deployment.spec.template.spec.volumes.nfs.server
  - [Check documentation at: https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.19/](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.19/)



