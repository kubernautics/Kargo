# Kargo | CCIO KubeVirt Hypervisor
The Kargo toolkit builds a Kubernetes KubeVirt based hypervisor on linux.

### Purpose:
Virtual machines and the surrounding infrastructure to support them with scheduling, storage,
networking, and availability has become a commonplace comodity featureset across public clouds.

Kargo attempts to bring basic comodity cloud featuresets onto user provided hardware in the age
of gitops and declarative infrastructure as code with an emphasis on budget comodity hardware and
high performance scalable production like infrastructure modeling orchestration.

This currently novel approach brings many advantages including:
  - Know Results
  - Minimal build skill and effort requirements
  - Declarative Virtual Machine & Virtual Network Overlay Orchestration
  - Agnostic consistency across kubernetes and OS distributions

### Usage:
Install Dependencies
```
 dnf install podman
```
Clone Kargo repository
```
mkdir -p /root/kargo && \
podman run -it --rm -v /root/kargo:/clone:z \
  quay.io/cloudctl/git https://github.com/ContainerCraft/Kargo.git && cd /root/kargo
```
Enable ssh to self
```
[[ -f ${HOME}/.ssh/id_rsa ]] || ssh-keygen -f ${HOME}/.ssh/id_rsa -t rsa -N ''
cat ${HOME}/.ssh/id_rsa.pub >> ${HOME}/.ssh/authorized_keys
chmod 0644 ${HOME}/.ssh/authorized_keys
ssh localhost whoami
```
Run Konductor Kargo Playbook
```
./kargo.sh -e kargo_host='192.168.1.105'
```
