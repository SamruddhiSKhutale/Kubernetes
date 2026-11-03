kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml
#Verify:
kubectl get deployment metrics-server -n kube-system
kubectl top nodes
kubectl top pods

#Apply your YAML files
kubectl apply -f nginx-deployment.yml
kubectl apply -f nginx-hpa.yml

#Check autoscaling:
kubectl get hpa
kubectl get pods -w
kubectl get hpa -w

#Verify everything
kubectl top nodes
kubectl top pods
kubectl get hpa
kubectl get pods -o wide
kubectl get nodes
kubectl get events --sort-by=.metadata.creationTimestamp
