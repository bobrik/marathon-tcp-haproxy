# Haproxy as tcp proxy for marathon

This is dockerized version of haproxy for marathon.

Haproxy allows you to allocate port number in marathon and
autmatically proxy all connections to your port on loopback
interface to instances running anywhere on mesos.

It is a good idea to run this on every mesos slave.

## Usage

```
docker run -d --net=host -e RELOAD_TTL=10 -e DISCOVERY_URL=localhost:8080 bobrik/marathon-tcp-haproxy
```

Here `RELOAD_TTL` is interval to check marathon for new port mappings
and `DISCOVERY_URL` is marathon host and port.

You can also set `HAPROXY_HOST` to specify ip address for haproxy (`127.0.0.1` by default).
