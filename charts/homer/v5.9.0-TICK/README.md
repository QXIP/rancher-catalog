<img src="https://camo.githubusercontent.com/fa828ea477eadd7e17a7814bae9946fea34e4c8b/687474703a2f2f692e696d6775722e636f6d2f566958634741442e706e67" width=400 />

# Homer 5.9 + TICK Stack

[Homer](https://www.sipcapture.org/) is an open-source VoIP and RTC Monitoring stack, powered by JSON-like documents with dynamic schemas and Timeseries backends.

### Introduction

This chart bootstraps a [Homer](https://github.com/sipcapture/homer) 5.9 deployment on a [Kubernetes](http://kubernetes.io) cluster using the [Helm](https://helm.sh) package manager.

#### Components
* HEP Stack
  * HOMER WebApp
  * HEPlify-Server
  * MySQL
* TICK Stack
  * Telegraf
  * InfluxDB
  * Chronograf
  * Kapacitor
  
### Usage Notes
In this version, there are NO STATS available in the HOMER, just search. All timeseries are in InfluxDB!

When dealing with prometheus counters in InfluxDB, refer to the following example usage of `difference` and `derivative` functions when selecting:
```
SELECT difference(last("counter")) AS "mean_counter" FROM "homer"."autogen"."heplify_method_response" WHERE time > :dashboardTime: GROUP BY time(:interval:), "method", "response" FILL(null)
```
```
SELECT derivative(last("counter")) AS "mean_counter" FROM "homer"."autogen"."heplify_method_response" WHERE time > :dashboardTime: GROUP BY time(:interval:), "method", "response" FILL(null)
```

![image](https://user-images.githubusercontent.com/1423657/40862016-705d998a-65eb-11e8-8b03-e711b7b4498d.png)
