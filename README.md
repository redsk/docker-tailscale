# docker-server-tailscale

A remote docker server for easing the pain of docker on Apple Silicon.

Build docker image in the `docker-image` directory (optional):
```bash
docker buildx build --platform linux/amd64 -t redsk/tailscale-remote-docker:1.20.1-1 --push .
```

Deploy Helm chart (assumes you have EBS storage class available in your AWS cluster), 
from the `helm-chart/tailscale-relay` directory:
```bash
helm -n remotedocker upgrade --install \
  docker-server \
  . \
  --set config.authKey=<your auth key> \
  --set image.repository=docker.io/redsk/tailscale-remote-docker \
  --set image.tag=1.20.1-1 \
  --set 'securityContext.privileged=true' \
  --set volumeSize=100Gi
```
