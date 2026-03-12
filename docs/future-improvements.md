# Future Improvements

The current DNS infrastructure provides a strong foundation for the homelab.  
Several improvements are planned to expand the environment into a more complete infrastructure platform.

---

# Dedicated Compute Server

A small server will be added to host applications and container workloads.

Planned hardware:

Mini PC

Responsibilities:

- Docker container hosting
- internal services
- monitoring stack
- reverse proxy and TLS termination

Example services:

```
grafana.lab.frost.vip
portainer.lab.frost.vip
git.lab.frost.vip
```

---

# Reverse Proxy and TLS

A reverse proxy will be introduced to provide HTTPS for internal services.

Possible solutions:

- Caddy
- Traefik
- Nginx Proxy Manager

Benefits:

- automatic TLS certificates
- centralized routing
- easier service management

---

# Monitoring and Observability

A monitoring stack will be implemented to observe system health.

Planned tools:

- Grafana
- Prometheus
- Node Exporter

This will provide:

- system metrics
- infrastructure monitoring
- alerting capabilities

---

# Security Monitoring

A security monitoring system will be deployed using:

Wazuh

Capabilities:

- intrusion detection
- log analysis
- vulnerability monitoring
- host-based security monitoring

This will allow the homelab to simulate enterprise security monitoring practices.

---

# Network Storage (NAS)

A Network Attached Storage system will be introduced to provide centralized storage.

Responsibilities:

- file storage
- backups
- media storage
- lab data storage

Potential solutions:

- TrueNAS
- Unraid
- Synology

Possible uses:

- personal cloud storage
- lab configuration backups
- shared storage for services

---

# Internal Cloud Storage

The NAS may be extended with self-hosted cloud software.

Possible solutions:

- Nextcloud
- Seafile

Benefits:

- private cloud storage
- file synchronization
- secure remote access to personal files

---

# Infrastructure Automation

Future improvements may include infrastructure automation tools.

Potential tools:

- Ansible
- Terraform
- Docker Compose

Goals:

- automate lab deployment
- rebuild infrastructure quickly
- improve configuration management

---

# Additional Homelab Services

Additional services may include:

- Gitea (self-hosted Git)
- Vaultwarden (password manager)
- Home automation integrations
- development environments

---

# Long-Term Goals

The long-term goal of this lab is to simulate real cloud and infrastructure environments.

This includes:

- production-style architecture
- infrastructure documentation
- monitoring and security tooling
- containerized services
- automation and infrastructure-as-code