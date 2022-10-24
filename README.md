# Monitoring and Logging

## Monitoring

### Prometheus & Grafana

```shell
helm install prometheus ./kube-prometheus-stack -f ./kube-prometheus-stack/values.yaml 
```

### values 변경점

- `additionalPrometheusRulesMap` 수정

- `additionalScrapeConfigs` 수정

### Delete
```shell
helm uninstall prometheus
```

## Logging

EleasticSearch -> kibana -> metricbeat 순으로 설정

### ElasticSearch

```shell
helm install elasticsearch ./elasticsearch -f ./elasticsearch/values.yaml 
```

### kibana

```shell
helm install kibana ./kibana -f ./kibana/values.yaml
```

### metricbeat

```shell
helm install metricbeat ./metricbeat -f ./metricbeat/values.yaml 
```

### Delete
```shell
helm uninstall elasticsearch
helm uninstall kibana
helm uninstall metricbeat
```