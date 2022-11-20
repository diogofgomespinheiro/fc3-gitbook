# 🌐 Network

## <mark style="color:purple;">Network types</mark> <a href="#network-types" id="network-types"></a>

### <mark style="color:orange;">Bridge</mark> <a href="#bridge" id="bridge"></a>

The default network driver. If you don’t specify a driver, this is the type of network you are creating. **Bridge networks are usually used when your applications run in standalone containers that need to communicate.** See [bridge networks](https://docs.docker.com/network/bridge/).

### <mark style="color:orange;">Host</mark> <a href="#host" id="host"></a>

For standalone containers, remove network isolation between the container and the Docker host, and use the host’s networking directly. See [use the host network](https://docs.docker.com/network/host/).

### <mark style="color:orange;">Overlay</mark> <a href="#overlay" id="overlay"></a>

Overlay networks connect multiple Docker daemons together and enable swarm services to communicate with each other. You can also use overlay networks to facilitate communication between a swarm service and a standalone container, or between two standalone containers on different Docker daemons. This strategy removes the need to do OS-level routing between these containers. See [overlay networks](https://docs.docker.com/network/overlay/).

### <mark style="color:orange;">Ipvlan</mark> <a href="#ipvlan" id="ipvlan"></a>

IPvlan networks give users total control over both IPv4 and IPv6 addressing. The VLAN driver builds on top of that in giving operators complete control of layer 2 VLAN tagging and even IPvlan L3 routing for users interested in underlay network integration. See [IPvlan networks](https://docs.docker.com/network/ipvlan/).

### <mark style="color:orange;">Macvlan</mark> <a href="#macvlan" id="macvlan"></a>

Macvlan networks allow you to assign a MAC address to a container, making it appear as a physical device on your network. The Docker daemon routes traffic to containers by their MAC addresses. Using the `macvlan` driver is sometimes the best choice when dealing with legacy applications that expect to be directly connected to the physical network, rather than routed through the Docker host’s network stack. See [Macvlan networks](https://docs.docker.com/network/macvlan/).

### <mark style="color:orange;">None</mark> <a href="#none" id="none"></a>

For this container, disable all networking. Usually used in conjunction with a custom network driver. `none` is not available for swarm services. See [disable container networking](https://docs.docker.com/network/none/).

## <mark style="color:purple;">Host DNS</mark> <a href="#host-dns" id="host-dns"></a>

### <mark style="color:orange;">For containers:</mark> <a href="#for-containers" id="for-containers"></a>

```bash
--add-host=host.docker.internal:host-gateway
```

### <mark style="color:orange;">For docker-compose:</mark>

```yaml
version: '3.7'
services:
  fpm:
    build:
      context: .
    extra_hosts:
      - "host.docker.internal:host-gateway"

```

{% embed url="https://stackoverflow.com/questions/48546124/what-is-linux-equivalent-of-host-docker-internal" %}
