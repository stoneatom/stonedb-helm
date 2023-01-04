# StoneDB Helm Chart

* Install the [StoneDB](https://stoneatom.com/StoneDB) on kubernetes

## TL;DR;

```console
$ helm repo add my-repo https://stoneatom.github.io/stonedb-helm
$ helm install my-release my-repo/stonedb-helm
```

## Install

To install the chart with the release name `my-release`:

```console
$ helm install my-release my-repo/stonedb-helm
```

## Uninstall

To uninstall/delete the my-release statefulSet:

```console
$ helm delete my-release
```

The command removes all the Kubernetes components associated with the chart and deletes the release.


## Configuration

| Parameter              | Description                              | Default         |
|------------------------|------------------------------------------|-----------------|
| `nameOverride`         | Name override                            | `stonedb`       |
| `replicaCount`         | Number of nodes                          | `1`             |
| `image.repository`     | Imgage repository                        | `stoneatom/stonedb` |
| `image.tag`            | Image tag                                | `latest`        |
| `image.pullPolicy`     | Image pull policy                        | `IfNotPresent`  
| `image.pullSecret`     | Image pull Secret                        | 
| `service.type`         | Kubernetes service type                  | `ClusterIP`     |
| `service.port`         | Kubernetes port where service is exposed | `3306`          |
| `pvc.enable`           | Create kubernetes pvc                    | `true`          |
| `pvc.size`             | Size of pvc                              | `100Gi`         |
| `pvc.storageClassName` | Storage class name of pvc                | `local-path`    |
| `pvc.accessMode`       | Access mode of pvc                       | `ReadWriteOnce` |
| `configmap.enabled`    | Create kubernetes configmap for my.cnf   | `true`          |
| `configmap.serverId`   | serverId for my.cnf                      | `1`             |
| `env.password`         | root password for stonedb                | `Aa123456`      |
