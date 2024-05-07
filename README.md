Run the commands in the following order:

``` bash
kubectl apply -f 00-namespace/
kubectl apply -f 01-zookeeper/
kubectl apply -f 02-kafka/

```

## Monitor cluster resources

``` bash
kubectl -n kafka-ca1 get pods
kubectl -n kafka-ca1 get deployments
kubectl -n kafka-ca1 describe pod kafka-0
kubectl delete -n kafka-ca1
```

## Logs
```bash
kubectl -n kafka-ca1 exec kafka-0 -- tail -f /opt/kafka/logs/state-change.log
kubectl -n kafka-ca1 exec kafka-0 -- tail -f /opt/kafka/logs/server.log
kubectl -n kafka-ca1 exec kafka-0 -- tail -f /opt/kafka/logs/controller.log
```


## Cluster view

<img src="resources/namespace-overview.png" width="40%">


# Changelog

- 2024-05-7, Forked from [original repo](https://github.com/d1egoaz/minikube-kafka-cluster) because docker kafka image was deleted. Also some services were deleted.
