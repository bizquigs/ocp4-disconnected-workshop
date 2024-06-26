# OpenShift 4 Disconnected Workshop
This repository contains the automation and instructions for the OpenShift Disconnected workshop.

GitHub Actions will update the rendered version of the instructions after every commit to the `main` branch.

[https://naps-product-sa.github.io/ocp4-disconnected-workshop/](https://naps-product-sa.github.io/ocp4-disconnected-workshop/)

Alternatively, you can rendering the workshop instructions locally using:

macOS
```bash
mkdir output
podman run -it --rm \
  -v `pwd`:/showroom/repo \
  --mount 'type=tmpfs,dst=/showroom/repo/.cache,chown=true' \
  -w /showroom/repo \
  --entrypoint antora \
  ghcr.io/rhpds/showroom-content:latest --to-dir=output default-site.yml
open output/index.html
```

Linux
```bash
mkdir output
podman run -it --rm \
  -v `pwd`:/showroom/repo:U,Z \
  --mount 'type=tmpfs,dst=/showroom/repo/.cache,chown=true' \
  -w /showroom/repo \
  --entrypoint antora \
  ghcr.io/rhpds/showroom-content:latest --to-dir=output default-site.yml
python3 -m http.server 8080 --dir output/
```
