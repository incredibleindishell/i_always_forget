NameSpace

#### Select specific namespace

    kubectl config set-context --current --namespace=my_name_space
#### list them all

    └──╼ #./kubectl get namespace


### Network Policies:
 #### Get them

    └──╼ #./kubectl get networkpolicy <-- for all namespaces
    
    └──╼ #./kubectl get networkpolicy --namespace=my_namespace  <-- for particular NS

 #### Describe them
      
    └──╼ #./kubectl describe networkpolicy --namespace=my_namespace  <-- for particular NS


### Security Context 

   To list the security context of the containers running in the Kube cluster, use script `security_context.sh`

### 


### Secrets

Listing secrets in a particular namespace:
   
     └──╼ #kubectl get secret --namespace your_namespace -o yaml

### services and ingress

Listing services:

     ┌─[root@IndiShell-lab]─[~]
     └──╼ #kubectl get service -A

Getting ingress detail:

     └──╼ #kubectl get ingress kube-prometheus-stack-grafana --namespace=monitoring -o yaml
