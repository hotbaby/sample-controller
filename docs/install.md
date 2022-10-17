# INSTALL



配置go环境：

```shell
export GOPROXY=https://goproxy.cn,direct
export GO111MODULE=on	
```

下载代码：

```shell
git@github.com:hotbaby/sample-controller.git
```

构建：

```shell
go build -o sample-controller .
./sample-controller -kubeconfig=$HOME/.kube/config

# create a CustomResourceDefinition
kubectl create -f artifacts/examples/crd-status-subresource.yaml

# create a custom resource of type Foo
kubectl create -f artifacts/examples/example-foo.yaml

# check deployments created through the custom resource
kubectl get deployments
```

代码生成：

```shell
GO111MODULE=on go mod vendor;

./hack/update-codegen.sh
```

