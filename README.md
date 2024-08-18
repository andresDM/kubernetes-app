
# Push chart
Install helm-push plugin
```
helm plugin install https://github.com/chartmuseum/helm-push
```

Port forward to chartmuseum hosted in minikube cluster
```
kubectl port-forward svc/chart-museum-argo-application-chartmuseum 8150:8080 -n chartmuseum
```

Add repo and push chart

```
helm repo add chartmuseum-local http://localhost:8150
```
Adjust the "version" field in the Chart.yaml file

```
helm cm-push kubernetes-app/ chartmuseum-local
```