This repository shares sample files used to monitor Horcrux metrics.


## Prometheus Configuration for Horcrux

[Sample Prometheus Configuration](https://github.com/chillyvee/horcrux-info/raw/master/prometheus/prometheus.yml "Sample Prometheus Configuration") to provide Grafana with information.


## Grafana Dashboard for Horcrux

A sample Grafana configration is available.  See [`horcrux.json`](https://github.com/chillyvee/horcrux-info/blob/master/grafana/horcrux.json)

![Sample Grafana Dashboard](https://github.com/chillyvee/horcrux-info/raw/master/grafana/grafana.png "Sample Grafana Dashboard").



## How to enable Prometheus 

We have the prometheus metrics enabled in a feature branch here:
https://github.com/chillyvee/horcrux/tree/add_prometheus

It's currently awaiting review from the team in a pending PR so feel free to try it on a testnet.
https://github.com/strangelove-ventures/horcrux/pull/93

## Prometheus labeling note:
Since node IP+Port can take a lot of space in displays, we tag each node with a share label.

```
scrape_configs:
  - job_name: "prometheus"
    static_configs:
            - targets: ["1.1.1.1:2001" ]
              labels: { "chain":"demo-1", "share":"1" }
            - targets: ["2.2.2.2:2002"]
              labels: { "chain":"demo-1", "share":"2" }
            - targets: ["3.3.3.3:2003"]
              labels: { "chain":"demo-1", "share":"3" }
```

A full example can be seen here:
https://github.com/chillyvee/horcrux-info/blob/master/prometheus/prometheus.yml#L30
