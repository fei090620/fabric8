## Pods

[Pods](https://github.com/GoogleCloudPlatform/kubernetes/blob/master/DESIGN.md#pods) are a Kubernetes concept which maps to one or more docker containers running on the same host. Typically in a fabric8 context this maps to a single container. 

Though a pod abstraction allows you to co-locate multiple containers together on a single box. e.g. a httpd container and 2 tomcat containers; or a wildfly and a redis container etc.

The pod JSON defines:

* docker container images 
* host and container ports (which since each pod gets it's own IP address are both constant; unlike when just using vanilla docker on a host)
* environment variables & linking 
* volume mounts for persistent disks (volumes can be shared in avoid between its containers)

The containers generated by a pod can have [labels](labels.html) so that containers can be filtered to create [Services](services.html).

