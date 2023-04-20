

### Network Policies:
 #### Get them

    └──╼ #./kubectl get networkpolicy <-- for all namespaces
    
    └──╼ #./kubectl get networkpolicy --namespace=my_namespace  <-- for particular NS

 #### Describe them
      
    └──╼ #./kubectl describe networkpolicy --namespace=my_namespace  <-- for particular NS


### Security Context 

   To list the security context of the containers running in the Kube cluster, use script `security_context.sh`

