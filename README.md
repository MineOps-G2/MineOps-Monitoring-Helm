# Monitoring and Logging

## Monitoring

```shell
kubectl create ns monitoring
```

### Prometheus & Grafana

```shell
helm install -n monitoring prometheus ./kube-prometheus-stack -f ./kube-prometheus-stack/values.yaml 
```

### Delete
```shell
helm uninstall -n monitoring prometheus
```

## Logging

EleasticSearch -> kibana -> metricbeat 순으로 설정
```shell
kubectl create ns logging
```

### ElasticSearch

```shell
helm install -n logging  elasticsearch ./elasticsearch -f ./elasticsearch/values.yaml 
```

### kibana

```shell
helm install -n logging kibana ./kibana -f ./kibana/values.yaml
```

### metricbeat

```shell
helm install -n logging metricbeat ./metricbeat -f ./metricbeat/values.yaml 
```

### Delete
```shell
helm uninstall -n logging elasticsearch
helm uninstall -n logging kibana
helm uninstall -n logging metricbeat
```