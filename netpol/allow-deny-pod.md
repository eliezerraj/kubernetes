// Curl POD test
k run test --image=alpine/curl --command sleep 3600

kubectl run mypod --image=nginx --labels="app=mypod" --expose --port=80

kind: NetworkPolicy
apiVersion: networking.k8s.io/v1
metadata:
  name: mypod-deny-all
spec:
  podSelector:
    matchLabels:
      app: mypod
  ingress: []


kind: NetworkPolicy
apiVersion: networking.k8s.io/v1
metadata:
  name: mypod-allow-all
spec:
  podSelector:
    matchLabels:
      app: mypod
  ingress: 
  - {}