URL: https://dashboard.k8s.the-hoffmanns.org/c/main/namespaces
Token Command: kubectl create token headlamp --namespace headlamp

helm upgrade --install headlamp headlamp/headlamp \
  --namespace headlamp \
  --create-namespace \
  --set ingress.enabled=true \
  --set ingress.ingressClassName=traefik \
  --set ingress.annotations."cert-manager\.io/cluster-issuer"=letsencrypt-prod \
  --set ingress.hosts[0].host=dashboard.k8s.the-hoffmanns.org \
  --set ingress.hosts[0].paths[0].path=/ \
  --set ingress.hosts[0].paths[0].type=Prefix \
  --set ingress.tls[0].secretName=headlamp-tls \
  --set ingress.tls[0].hosts[0]=dashboard.k8s.the-hoffmanns.org
