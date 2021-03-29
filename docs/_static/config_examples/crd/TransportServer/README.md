# Unsecured Transport Server

A Standard virtual server in BIG-IP has configurable settings that allow you to customize what traffic is processed by the virtual server. 
Transport Server CRD can be used for L4 traffic protocols. As of today, CIS supports Transmission Control Protocol (TCP) and User Datagram Protocol (UDP)
This section demonstrates the deployment of unsecured Transport Servers.

User may be able to expose non-http traffic such as databases via CIS using Transport Server CRD.
The TransportServer only forwards the traffic. It is the user’s responsibility to implement secure non-http traffic.
CIS VirtualServer CRD implements a full proxy architecture for virtual servers configured with a HTTP profile allowing Layer 7 load balancing and SSL processing.

## TCP Transport Server

* TCP mode is the default type of transport server. 
* By deploying `tcp-transport-server.yaml` yaml file in your cluster, CIS will create a TCP Virtual Server on BIG-IP with VIP "172.16.3.9" and port "8544". It will forward traffic to specified pool.

## UDP Transport Server

* For UDP type transport servers, yaml spec should contain a `type` parameter. Refer `udp-transport-server.yaml` example for more details
* By deploying `udp-transport-server.yaml` yaml file in your cluster, CIS will create a UDP Virtual Server on BIG-IP with VIP "172.16.3.10" and port "8444". It will forward traffic to specified pool.
