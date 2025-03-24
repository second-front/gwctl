# gwctl
A cli tool for deploying a small Game Warden like cluster.

## Welcome to gwctl

## Install

### Linux & MacOS
> [!NOTE]
> Update the version, os, and arch variable for your needs.
```sh
version=0.0.0
os=linux
arch=amd64
curl -LO "https://github.com/second-front/gwctl/releases/download/$version/gwctl_${version}_${os}_${arch}.tar.gz" && tar -xzvf "gwctl_${version}_linux_amd64.tar.gz" -C /usr/local/bin
# To verify with cosign (replace <COSIGN_PUBLIC_KEY> with your key):
curl -LO "https://github.com/second-front/gwctl/releases/download/$version/gwctl_${version}_${os}_${arch}.tar.gz.sig"
curl -LO "https://github.com/second-front/gwctl/releases/download/$version/cosign.pub"
cosign verify-blob --key cosign.pub --signature "gwctl_${version}_.${os}_${arch}.tar.gz.sig" "gwctl_${version}_${os}_${arch}.tar.gz"
```

### Basic usage
This will generate a gitops configuration in a folder named `gw-gitops` to apply to an existing k8s cluster with flux installed.
```sh
gwctl config init
```
or
You can create a local kind cluster to apply the configuration to for local testing.
```sh
# From the root of the generated gw-gitops repo
gwctl cluster create
```

### Issues
Please file any issues [here](https://github.com/second-front/gwctl/issues) as you encounter them.
