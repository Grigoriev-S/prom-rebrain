# PROM FINAL

## Grafana:

- Node_exporter: https://prnt.sc/pBJKTLGePAax
- Mysqld: https://prnt.sc/4SdNX8Pu6mOp
- Cadvisor: https://prnt.sc/Kdg4ffs476iT

## Prometheus:
```
# my global config
global:
  scrape_interval: 15s # Set the scrape interval to every 15 seconds. Default is every 1 minute.
  evaluation_interval: 15s # Evaluate rules every 15 seconds. The default is every 1 minute.
  # scrape_timeout is set to the global default (10s).

# Alertmanager configuration
alerting:
  alertmanagers:
    - static_configs:
        - targets:
          # - alertmanager:9093
# A scrape configuration containing exactly one endpoint to scrape:
# Here it's Prometheus itself.
scrape_configs:
  # The job name is added as a label `job=<job_name>` to any timeseries scraped from this config.
  - job_name: "prometheus"
    static_configs:
      - targets: ["localhost:9090"]
  - job_name: 'node'
    static_configs:
      - targets: ['116.203.29.13:9100']
  - job_name: 'cadvisor'
    static_configs:
      - targets: ['116.203.29.13:8080']
  - job_name: 'mysqld'
    static_configs:
      - targets: ['116.203.29.13:9104']
```
## Logs:
см файлы:
 -  cadvisor.log
 -  mysqld_exporter.log
 -  node_exporter.log
