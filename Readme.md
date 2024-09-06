# EIB demo 

This repo contains eib demo example for community only sharing.

## Image source

Please get the SLE micro 5.5 from scc, https://www.suse.com/download/sle-micro/. Select 5.5 and selfinstall image(SLE-Micro.x86_64-5.5.0-Default-SelfInstall-GM2.install.iso). Download it under dir `./demo-code/base-images`

## Remark

- Root password generating command: `openssl passwd -6 P@ssw0rd`
- The kube-explorer HTTP base auth generating command: `htpasswd -nb admin P@ssw0rd | base64`
- EIB build command: `docker run --rm -it -v ${PWD}:/eib -e https_proxy --privileged registry.suse.com/edge/edge-image-builder:1.0.2 build --definition-file definition.yaml`. Both docker and podman are fine.
- Some of the variables in the configuration need to be replaced with the actual deploy environment value. e.g. mac address in network configuration, and the fqdn address of the kube-explorer ingress.
