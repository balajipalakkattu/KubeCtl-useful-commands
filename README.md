# KubeCtl-useful-commands
Solution to the Error: Unable to connect to the server: x509: certificate signed by unknown authority (possibly because of "crypto/rsa: verification error" while trying to verify candidate authority certificate "ca") 

Reset Context:  

az login 

az account set --subscription "SUBSCRIPTION-NAME" 


kubectl config set-context --current --namespace=NAME-SPACE 

 

az aks get-credentials -n <name space> --resource-group <resource gropu> --subscription "subscription name" 

 

 

kubectl.exe get pods -n <namespace> 


From the pod name describe it to get the start up details 


kubectl describe -n NAME-SPACE pod POD-INSTANCE-NAME-bc448b968-64hn2 

 

 

 

kubectl logs <deploy name> -n <name space> 

kubectl logs -n dev-NAME-SPACE POD-INSTANCE-NAME-79cfd7cd6d-r7rd6 

 

Terminate all instances 

Kubectl get deploy -n <name space> : Lists all deployments 

Kubectl get deploy –n NAME-SPACE 

 

kubectl scale deployment <deployment name from get deploy command> --replicas=0 -n <name space> 

 
 

kubectl scale deployment <pod instance name> --replicas=1 -n <name space> 

 

 

Note: If you have the configuration created, use as follows 

 Export KUBECONFIG="path/to/the/config/file" 

Kubectl get pods 

kubectl.exe get all --- lists all pod, services, deployment.apps, replicaset.apps 

kubectl/kubectl.exe delete deployment.apps/<deploymentname> service/<servicename>
 
 #Service Account with jq
 echo $(kubectl get secret --namespace "${NAMESPACE}" "${SECRET_NAME}" -o json | jq-win64.exe -r '.data["ca.crt"]') 

printf "token\\n" 

echo $(kubectl get secret --namespace "${NAMESPACE}" "${SECRET_NAME}" -o json | jq-win64.exe -r '.data["token"]') 

printf "namespace\\n" 

echo $(kubectl get secret --namespace "${NAMESPACE}" "${SECRET_NAME}" -o json | jq-win64.exe -r '.data["namespace"]') 

 

Certificate: Copy from terminal 

Token: Base64 Decode 
