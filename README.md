# docker-server-tailscale

A remote docker server for easing the pain of docker on Apple Silicon.

Build docker image in the `docker-image` directory:
```bash
docker buildx build --platform linux/amd64 -t redsk/tailscale-remote-docker:0.0.11 --push .
```

Deploy Helm chart (assumes you have EBS storage class available in your AWS cluster):
```bash
helm -n remotedocker upgrade --install \
  docker-server \
  . \
  --set config.authKey=<your auth key> \
  --set image.repository=docker.io/redsk/tailscale-remote-docker \
  --set image.tag=0.0.11 \
  --set 'securityContext.privileged=true' \
  --set volumeSize=100Gi
```
