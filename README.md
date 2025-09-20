# minikube local
cmd: (build image)
eval $(minikube docker-env)
docker build -t my-nginx .

Confirm it's built:
docker images | grep my-nginx

Apply the resources: 
kubectl apply -f simple-pod.yml
kubectl apply -f nginx-service.yml   # if you have a Service

Port-Forward to test:
kubectl port-forward pod/nginx-pod 8080:80 (use a different terminal if possible) 

Open browser: 
http://localhost:8080
