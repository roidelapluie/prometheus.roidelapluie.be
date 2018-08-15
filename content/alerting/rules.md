# Alerting rules

```
groups:
- name: alertmanager
  rules:
  - alert: Alertmanager configurations are out of sync
    expr: count(count_values("config", alertmanager_config_hash)) != 1
    for: 2h
  - alert: Alertmanager configuration is not loaded properly
    expr: alertmanager_config_last_reload_successful != 1
    for: 5m
```
