# docker-systemd

Base image for running systemd in a container.

### Example Usage

Create a sample Dockerfile.

```Dockerfile
FROM quay.io/ukhomeofficedigital/systemd

RUN dnf upgrade -y && dnf install rkt -y && dnf clean all

CMD ["/usr/sbin/init"]
```

Build it.
```
docker build -t rkt .
```

Rut it.
```
docker run -ti --privileged -v /sys/fs/cgroup:/sys/fs/cgroup:ro rkt
```
