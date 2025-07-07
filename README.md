# Tor Relay Grafana Monitoring Dashboard
A Grafana dashboard that provides a in depth of your tor relay analistics live. It enables real time monitoring of many things such as: 
- Relay status and uptime
- Connection load and socket usage
- Bandwidth and traffic flow (bps and cumulative)
- Circuit processing performance
- Onionskin handling
- DoS protection events
- IPv4 vs IPv6 distribution
- Exit, directory, and OR traffic patterns
- Memory and congestion indicators

##  Requirements
To use this dashboard, you need to expose your Tor MetricsPort in /etc/tor/torrc, which will then be scraped by Prometheus.

Example: `/etc/tor/torrc`
```
MetricsPort 0.0.0.0:9035 prometheus
MetricsPortPolicy accept <IP>
```
https://tpo.pages.torproject.net/onion-services/onionspray/guides/monitoring/


Example: Prometheus Configuration
```jaml
- job_name: 'tor-exit'
  metrics_path: /metrics
  scheme: http
  static_configs:
    - targets: ['<IP>:9035']
```
You can add as many targets as you want.

## Preview
(The bars are just the result of the screenshotting process)

![screencapture-stats-exulan-au-d-cer48kf7661oga-tor-relay-monitoring-2025-07-07-21_38_18](https://github.com/user-attachments/assets/11894e1f-092c-4816-b443-9d83bdf0cb9e)

