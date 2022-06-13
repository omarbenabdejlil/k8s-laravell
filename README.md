# k8s-laravell 
## Deploying Laravel App on Kubernetes cluster locally 
<img src="https://kubernetes.io/images/kubernetes-horizontal-color.png">

### To deploy the application on the k8s cluster please try the following  steps : 
```bash
kubectl apply -f php_service.yaml 
```
* To list services type `kubectl get services` || `kubectl get svc` 
```bash
kubectl apply -f php_deployment.yaml
```
* To grab the @ip of the php service type `kubectl get endpoints php` 
#### [ ! ] You need to put this @ip in the fastcgi_pass variable of the `nginix_configMap.yaml` or put the name of the service as exemple `php` 

```bash
kubectl apply -f nginix_configMap.yaml
```
```bash
kubectl apply -f nginix_deployment.yaml
```
- To get the URL of the app , just type `kubectl get services` to get the name then `minikube service nginx-service` to get the URL . 
