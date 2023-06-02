# jellyfin-kubernetes

This is a Helm chart repo for [jellyfin-rffmpeg](https://github.com/aleksasiriski/jellyfin-rffmpeg) and [jellyfin-rffmpeg-intro-skipper](https://github.com/aleksasiriski/jellyfin-rffmpeg-intro-skipper)

## Kubernetes

On Kubernetes you can use [Longhorn](https://longhorn.io) RWX volumes (NFSv4) and mount said paths to Jellyfin host and workers (must be exactly the same mount points!).

Here's an example [deployment]() of workers. Then just add it as a rffmpeg host:

```bash
kubectl exec -n jellyfin jellyfin-0 -- rffmpeg add --name rffmpeg-workers rffmpeg-workers.jellyfin.svc.cluster.local
```