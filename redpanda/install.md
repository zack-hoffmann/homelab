helm repo add redpanda https://charts.redpanda.com
helm repo update
helm install redpanda redpanda/redpanda -n redpanda --wait
kubectl create secret generic console-auth-secret \
  --namespace redpanda \
  --from-literal=users='zack:foohash'
helm upgrade redpanda redpanda/redpanda \
  --namespace redpanda \
  --reuse-values \
  -f ingress.yaml

