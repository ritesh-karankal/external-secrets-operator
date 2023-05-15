Learned about external secrets opertor from Kubesimplify (https://youtu.be/V40tXvvKh5Y)
# external-secrets-operator

## Kubernetes cluster 
The first thing is a Kubernetes cluster that you need in order to do the demo 

## Vault installation 
```
kubectl create namespace vault
kubectl --namespace='vault' get all
helm repo add hashicorp https://helm.releases.hashicorp.com
helm search repo hashicorp/vault --versions
helm install vault hashicorp/vault --namespace vault --version 0.23.0
```

- Install Vault in your minikube cluster.
- Make modifications to the vault-internal service:
- Change the service type from ClusterIP to NodePort.
- Remove the "clusterIps: none" line to prevent errors.
- Save the changes, which will create a temporary file with a generic name.
- Delete the existing service.
- Apply the modified service configuration again.
- 
- After completing these steps, you can expect to access the Vault server at the following URL: https://<EXTERNAL_IP>:<NODEPORT>.
- Run the command `minikube service list` to list all services in your minikube cluster.
Look for the Vault service in the list and note the NodePort assigned to it (usually in the 30000-32767 range).
Open a web browser and enter the URL https://<EXTERNAL_IP>:<NODEPORT> (replace <NodePort> with the actual NodePort value from the previous step).

## Configure vault

Save the keys -> unseal vault -> enable the kv engine -> create the secret -> get the token to login to vault saved.


## Install external secrets operator

```
helm repo add external-secrets https://charts.external-secrets.io

helm install external-secrets \
   external-secrets/external-secrets \
    -n external-secrets \
    --create-namespace \
   --set installCRDs=true

```
## Create the secretstore and external secret
make sure to change the vault endpoint and token for your endpoint and you need to encode it as base64 before putting it in the file.
