---
title: "Warum ich Podman gegenüber Docker bevorzuge"
date: 2025-01-15
draft: false
tags: ["Container", "Podman", "Docker", "DevOps", "Linux"]
categories: ["Technologie"]
showToc: true
TocOpen: false
---

Als jemand, der intensiv mit Containern arbeitet und zu Fedoras Container-Tools beiträgt, bin ich von Docker zu Podman als primäre Container-Runtime gewechselt. Hier ist der Grund.

## Rootless von Haus aus

Podman führt Container ohne Root-Rechte aus. Das ist nicht nur ein Sicherheitsfeature – es verändert grundlegend, wie man über Container-Isolation nachdenkt.

```bash
# Kein sudo nötig
podman run -it fedora:latest
```

Dies ist besonders wichtig in Mehrbenutzerumgebungen und entspricht dem Prinzip der minimalen Rechte.

## Daemonlose Architektur

Docker benötigt einen im Hintergrund laufenden Daemon mit Root-Rechten. Podman nicht. Jeder Container ist ein Kindprozess des podman-Befehls, was bedeutet:

- Bessere Kompatibilität mit systemd
- Einfacheres Debugging
- Höhere Sicherheit (kein dauerhaft laufender Root-Daemon)

## Docker-Kompatibilität

Das Beste? Fast alles, was man über Docker weiß, lässt sich direkt übertragen:

```bash
alias docker=podman  # Das funktioniert tatsächlich für die meisten Anwendungsfälle
```

Podman versteht Dockerfiles, unterstützt dieselben CLI-Befehle und arbeitet mit Docker Compose (via podman-compose oder native Unterstützung).

## Native Pod-Unterstützung

Podman hat native Unterstützung für Pods – Gruppen von Containern, die Namespaces teilen. Das passt besser zu Kubernetes-Konzepten.

```bash
podman pod create --name myapp
podman run --pod myapp -d nginx
podman run --pod myapp -d redis
```

## Systemd-Integration

Generiere systemd-Unit-Dateien direkt aus laufenden Containern:

```bash
podman generate systemd --new --name mycontainer > mycontainer.service
```

## Fazit

Für Entwicklungs- und Produktions-Workloads bietet Podman bessere Sicherheitsstandards und eine sauberere Architektur bei gleichzeitiger Docker-Kompatibilität.
