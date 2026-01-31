---
title: "Why I Prefer Podman Over Docker"
date: 2025-01-15
draft: false
tags: ["Containers", "Podman", "Docker", "DevOps", "Linux"]
categories: ["Technology"]
showToc: true
TocOpen: false
---

As someone who works extensively with containers and contributes to Fedora's container tooling, I've made the switch from Docker to Podman as my primary container runtime. Here's why.

## Rootless by Default

Podman runs containers without requiring root privileges. This isn't just a security feature—it fundamentally changes how you think about container isolation.

```bash
# No sudo needed
podman run -it fedora:latest
```

This is particularly important in multi-user environments and aligns with the principle of least privilege.

## Daemonless Architecture

Docker requires a daemon running in the background with root privileges. Podman doesn't. Each container is a child process of the podman command, which makes it:

- More compatible with systemd
- Easier to debug
- More secure (no long-running root daemon)

## Docker Compatibility

The best part? Almost everything you know about Docker translates directly:

```bash
alias docker=podman  # This actually works for most use cases
```

Podman understands Dockerfiles, supports the same CLI commands, and works with Docker Compose (via podman-compose or native support).

## Native Pod Support

Podman has native support for pods—groups of containers sharing namespaces. This aligns better with Kubernetes concepts and makes it easier to develop applications that will eventually run in K8s.

```bash
podman pod create --name myapp
podman run --pod myapp -d nginx
podman run --pod myapp -d redis
```

## Systemd Integration

Generate systemd unit files directly from running containers:

```bash
podman generate systemd --new --name mycontainer > mycontainer.service
```

This makes it trivial to run containers as proper system services.

## Conclusion

For development and production workloads, Podman offers better security defaults and a cleaner architecture while maintaining Docker compatibility. If you're on Fedora, RHEL, or any systemd-based distribution, give it a try.
