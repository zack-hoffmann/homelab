# Homebridge on Kubernetes

Homebridge runs as a single pod in the `homebridge` namespace.

## Apply

Apply resources one at a time in dependency order:

```sh
kubectl apply -f homebridge/00-namespace.yaml
kubectl apply -f homebridge/10-persistent-volume.yaml
kubectl apply -f homebridge/20-persistent-volume-claim.yaml
kubectl apply -f homebridge/25-default-config.yaml
kubectl apply -f homebridge/30-deployment.yaml
kubectl apply -f homebridge/40-service.yaml
kubectl apply -f homebridge/50-ingress.yaml
```

Or apply the whole directory:

```sh
kubectl apply -f homebridge/
```

## DNS

Point `home.the-hoffmanns.org` at the cluster ingress address.

## Access

The admin UI is published through nginx ingress:

```text
https://home.the-hoffmanns.org/homebridge
```

HomeKit discovery depends on mDNS/Bonjour, so the pod uses `hostNetwork: true`.
Keep the deployment at one replica unless Homebridge is rebuilt around a different
discovery and storage model.

## Storage

Homebridge state is stored in the `homebridge-data` PVC and mounted at
`/homebridge` in the container. The PVC binds to a static NFS PersistentVolume
at `grist.the-hoffmanns.org:/apps/homebridge`.

## Troubleshooting

If nginx returns a generic `503 Service Temporarily Unavailable`, check whether the
`homebridge` service has endpoints. Homebridge UI may bind to IPv6 by default on
hosts with IPv6 enabled, while the service endpoint and readiness probe use IPv4.
Set the Config UI platform host in `/homebridge/config.json`:

```json
{
  "name": "Config",
  "port": 8581,
  "platform": "config",
  "host": "0.0.0.0"
}
```

The local deployment manifest includes an init container that seeds or patches this value before Homebridge starts.
