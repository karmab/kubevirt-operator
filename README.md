# kubevirt-operator
Operator that manages KubeVirt

## Quick Start

### Prerequisites

- Golang environment and GOPATH correctly set
- Docker (used for creating container images, etc.) with access for the current user
- a Kubernetes/OpenShift/Minikube/Minishift instance
- Operator SDK

### Dependencies

Get dep if you don't have it

```bash
go get -u github.com/golang/dep/cmd/dep
```

Checkout the project and its dependencies:

```bash
mkdir -p $GOPATH/src/github.com/kubevirt
cd $GOPATH/src/github.com/kubevirt
git clone https://github.com/kubevirt/kubevirt-operator
cd kubevirt-operator
git checkout master
make dep
```

### Compile it
```make compile```

### Build the Operator Container with the Operator SDK
```make build```

### Launch the Operator
```make deploy```

You will see
- a kubevirt-operator pod in your current namespace
- kubevirt components in the kube-system namespace
- a new custom resource definition (crd) called `virtualization.virt.kubevirt.io`
- an instance of this crd called `kubevirt` in your current namespace
