# Elasticsearch Chart
This chart is based on the [elasticsearch/elasticsearch](https://www.docker.elastic.co/) image.
 
# kibana
[kibana](https://github.com/elastic/kibana) is your window into the Elastic Stack. Specifically, it's an open source (Apache Licensed), browser-based analytics and search dashboard for Elasticsearch.

# Configurations

## Elasticsearch
The following table lists the configurable parameters of the elasticsearch chart and their default values.

|              Parameter               |                             Description                             |               Default                |
| ------------------------------------ | ------------------------------------------------------------------- | ------------------------------------ |
| `image.repository`                   | Container image name                                                | `docker.elastic.co/elasticsearch/elasticsearch-oss` |
| `image.tag`                          | Container image tag                                                 | `6.2.4`                              |
| `image.pullPolicy`                   | Container pull policy                                               | `IfNotPresent`                       |
| `master.exposeHttp`                  | Expose http port 9200 on master Pods for monitoring, etc            | `true`                               |
| `master.replicas`                    | Master node replicas (statefulset)                                  | `3`                                  |
| `master.resources`                   | Master node resources requests & limits                             | `{} - cpu limit must be an integer`  |
| `master.heapSize`                    | Master node heap size                                               | `512m`                               |
| `master.name`                        | Master component name                                               | `master`                             |
| `master.persistence.enabled`         | Master persistent enabled/disabled                                  | `true`                               |
| `master.persistence.name`            | Master statefulset PVC template name                                | `data`                               |
| `master.persistence.size`            | Master persistent volume size                                       | `10Gi`                                |
| `master.persistence.storageClass`    | Master persistent volume Class                                      | `nil`                                |
| `master.persistence.accessMode`      | Master persistent Access Mode                                       | `ReadWriteOnce`                      |
| `master.antiAffinity`                | Data anti-affinity policy                                           | `soft`                               |
| `rbac.create`                        | Create service account and ClusterRoleBinding for Kubernetes plugin | `false`                              |


## Kibana
The following table lists the configurable parameters of the kibana chart and their default values.

Parameter | Description | Default
--- | --- | ---
`affinity` | node/pod affinities | None
`env` | Environment variables to configure Kibana | `{}`
`image.pullPolicy` | Image pull policy | `IfNotPresent`
`image.repository` | Image repository | `kibana`
`image.tag` | Image tag | `6.0.0`
`image.pullSecrets` |Specify image pull secrets | `nil`
`commandline.args` | add additional commandline args | `nil`
`ingress.enabled` | Enables Ingress | `false`
`ingress.annotations` | Ingress annotations | None:
`ingress.hosts` | Ingress accepted hostnames | None:
`ingress.tls` | Ingress TLS configuration | None:
`nodeSelector` | node labels for pod assignment | `{}`
`podAnnotations` | annotations to add to each pod | `{}`
`replicaCount` | desired number of pods | `1`
`resources` | pod resource requests & limits | `{}`
`service.externalPort` | external port for the service | `443`
`service.internalPort` | internal port for the service | `4180`
`service.externalIPs` | external IP addresses | None:
`service.loadBalancerIP` | Load Balancer IP address (to use with service.type LoadBalancer) | None:
`service.type` | type of service | `ClusterIP`
`service.annotations` | Kubernetes service annotations | None:
`tolerations` | List of node taints to tolerate | `[]`


