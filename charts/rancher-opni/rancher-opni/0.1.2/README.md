# rancher-opni
A chart to install the Opni system into an existing kubernetes cluster.

Installs the opni-manager Operator, and an opnidemo custom resource.

## Requirements
 - 4 CPUs
 - 8GB of RAM

## Configuration

The following table lists the configurable parameters of the rancher-opni chart and their default values.
|                      Parameter                      |                        Description                     |             Default            |
| --------------------------------------------------- | ------------------------------------------------------ | ------------------------------ |
| `image.repository`                                  | Container image repository                             | `rancher/opni-manager`         |
| `image.tag`                                         | Container image tag                                    | `latest`                       |
| `image.pullPolicy`                                  | Container pull policy                                  | `IfNotPresent`                 |
| `distribution`                                      | Kubernetes distribution (rke, rke2, or k3s)            | `""`                           |
| `elastic.enabled`                                   | Install an opendistro elasticsearch stack              | `true`                         |
| `elastic.kibana.serviceType`                        | ServiceType for the Kibana install                     | `NodePort`                     |
| `rancherLogging.enabled`                            | Install and configure rancher-logging to ship to Opni  | `true`                         |
| `helmController.enabled`                            | Install helmController for prerequisite charts  (only set to false if a helmController is already installed)       | `true`        |
| `nvidiaPlugin.enabled`                              | Install the nVidia k8s GPU plugin                      | `false`                        |
| `nvidiaPlugin.version`                              | Version of the nVidia plugin to install                | `1.0.0-beta6`                  |
| `gpuServices.enabled`                               | Install services that require GPU (requires nvidiaPlugin.enabled to also be true) | `true` |
| `nats.replicas`                                     | Number of NATS pods (should be odd number)             | `3`                            |
| `nats.version`                                      | NATS image version                                     | `2.2.1`                        |
| `nulog.cpuRequest`                                  | CPU request for the nulog service                      | `1`                            |
| `nulog.trainImage`                                  | Image for nulog train (requires gpusService.enabled to be true) | `""`                  |