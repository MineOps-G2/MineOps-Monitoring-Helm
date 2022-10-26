# Monitoring and Logging

## Monitoring

### Prometheus & Grafana

- 사용할 slack webhook url을 넣어야 slack에서 알람을 받을 수 있습니다.

```shell
helm install prometheus ./kube-prometheus-stack -f ./kube-prometheus-stack/values.yaml --set alertmanager.config.global.slack_api_url="[slack_webhook_url]"
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

## fluent-bit

Fluent bit는 해당 폴더 [README.md](./fluent-bit/README.md) 파일을 참조

### Delete
```shell
helm uninstall elasticsearch
helm uninstall kibana
```