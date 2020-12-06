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
  
- `metadata:`
- `spec:`

