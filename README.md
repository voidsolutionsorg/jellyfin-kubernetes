# jellyfin-kubernetes

This is a Helm chart repo for [jellyfin-rffmpeg](https://github.com/aleksasiriski/rffmpeg-go/pkgs/container/jellyfin-rffmpeg) and [jellyfin-rffmpeg-intro-skipper](https://github.com/aleksasiriski/rffmpeg-go/pkgs/container/jellyfin-rffmpeg-intro-skipper)

### Kubernetes

On Kubernetes you can use [Longhorn](https://longhorn.io) RWX volumes (NFSv4) and mount said paths to Jellyfin host and workers (must be exactly the same mount points!).

You will need to generate an ssh key pair and add them as a secret using the commands below. Make sure this is done in the same namespace as the helm install.

```bash
ssh-keygen -t rsa -N '' -f ./id_rsa
kubectl create secret generic rffmpeg-ssh --from-file=./id_rsa --from-file=./id_rsa.pub
```
