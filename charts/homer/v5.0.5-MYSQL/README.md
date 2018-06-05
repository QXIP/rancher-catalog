<img src="https://camo.githubusercontent.com/fa828ea477eadd7e17a7814bae9946fea34e4c8b/687474703a2f2f692e696d6775722e636f6d2f566958634741442e706e67" width=400 />

# Homer 5.0.5 Classic (mysql)

[Homer](https://www.sipcapture.org/) is an open-source VoIP and RTC Monitoring stack, powered by JSON-like documents with dynamic schemas and Timeseries backends.

### Introduction

This chart bootstraps a [Homer](https://github.com/sipcapture/homer) 5.0.5 deployment on a [Kubernetes](http://kubernetes.io) cluster using the [Helm](https://helm.sh) package manager.

#### Components
* HEP Stack
  * HOMER WebApp
  * HEPlify-Server
  * MySQL
  * Telestats
* TICK Stack
  * Telegraf
  
### Usage Notes
In this version, statistics are converted from Prometheus to MySQL as per Classic Homer.
