# helm-hlf

## Preq

open vpn

```cmd
// https://scoop.sh/
// open powershell
irm get.scoop.sh | iex
scoop install helm
scoop install main/minikube
```



## helm install hyperledger

```
// 1. hlf-ca: 1.5.1, Chart version:2.1.0(23 Aug, 2022)
// https://artifacthub.io/packages/helm/owkin/hlf-ca
// originally(temp not work using minikube)
helm repo add owkin https://owkin.github.io/charts
helm install org1-ca owkin/hlf-ca --version 2.1.0
// download directly(also not work)
https://owkin.github.io/charts/hlf-ca-2.1.0.tgz
helm install org1-ca0 .\hlf-ca\

// 2. hlf-couchdb: 3.1.1, Chart version: 2.1.0(23 Aug, 2022)
// https://artifacthub.io/packages/helm/owkin/hlf-couchdb
helm repo add owkin https://owkin.github.io/charts
helm install my-hlf-couchdb owkin/hlf-couchdb --version 2.1.0
// download
https://owkin.github.io/charts/hlf-couchdb-2.1.0.tgz
helm install org1-cdb0 .\hlf-couchdb\

// 3. order: 2.2.1, Chart version: 3.1.0(23 Aug, 2022)
// https://artifacthub.io/packages/helm/owkin/hlf-ord
helm repo add owkin https://owkin.github.io/charts
helm install my-hlf-ord owkin/hlf-ord --version 3.1.0
// download
https://owkin.github.io/charts/hlf-ord-3.1.0.tgz
helm install org1-ord0 .\hlf-ord\

// 4. peer: 2.2.1, Chart verion: 5.1.0(23 Aug, 2022)
// https://artifacthub.io/packages/helm/owkin/hlf-peer
helm repo add owkin https://owkin.github.io/charts
helm install my-hlf-peer owkin/hlf-peer --version 5.1.0
// download
https://owkin.github.io/charts/hlf-peer-5.1.0.tgz
helm install org1-peer0 .\hlf-peer\
```

## docker images

```
docker pull mirror.baidubce.com/hyperledger/fabric-ca:1.5.1
docker pull mirror.baidubce.com/hyperledger/fabric-orderer:2.2.2
docker pull mirror.baidubce.com/hyperledger/fabric-peer:2.2.2
docker pull mirror.baidubce.com/couchdb:3.1.1
```

* fabric and couchdb version mapping

![image-20230815154227571](.\fabric-couchdb-version-mapping.jpg)

* fabric order/peer/ca version mapping

  https://www.ibm.com/docs/en/blockchain-platform/2.5.3?topic=help-release-notes#05-05-2021

  ![image-20230815164747568](.\fabric-ca-order-peer-version-mapping.jpg)