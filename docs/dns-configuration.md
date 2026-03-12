# Internal DNS Records

Internal DNS records are managed through AdGuard Home.

Domain:

```
lab.frost.vip
```

---

# Current Records

```
dns.lab.frost.vip       -> 192.168.0.179
adguard.lab.frost.vip   -> 192.168.0.179
router.lab.frost.vip    -> 192.168.0.1
compute.lab.frost.vip   -> future mini PC
```

---

# Purpose

Using an internal DNS namespace allows services to be addressed by name instead of IP.

This also prepares the environment for future services.

Example:

```
grafana.lab.frost.vip
portainer.lab.frost.vip
```