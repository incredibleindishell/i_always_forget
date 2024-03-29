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
     

### Tools for RBAC Mapping

https://github.com/cyberark/KubiScan
https://github.com/aquasecurity/kubectl-who-can

### Good resources regarding Kubernetes security:

https://cloud.hacktricks.xyz/pentesting-cloud/kubernetes-security/kubernetes-pivoting-to-clouds

https://cloud.hacktricks.xyz/pentesting-cloud/kubernetes-security/kubernetes-namespace-escalation

https://blog.christophetd.fr/privilege-escalation-in-aws-elastic-kubernetes-service-eks-by-compromising-the-instance-role-of-worker-nodes/

https://blog.calif.io/p/privilege-escalation-in-eks
