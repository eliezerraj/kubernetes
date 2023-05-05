kubectl create ns space3

kubectl run app1 --image=nginx --labels="app=app1" --expose --port=80
kubectl run app2 --image=nginx --labels="app=app2" --expose --port=80
kubectl run app3 --image=nginx --labels="app=app3" --namespace3 --expose --port=80