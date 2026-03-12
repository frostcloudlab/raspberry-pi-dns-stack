# Lessons Learned

This project provided hands-on experience with several networking concepts.

---

# Recursive DNS Resolution

Most home networks rely on public DNS providers such as:

- Google DNS
- Cloudflare DNS
- ISP DNS

This project implemented a fully recursive DNS resolver using Unbound.

This allowed DNS queries to be resolved directly from root DNS servers.

---

# DNS Filtering

Network-wide filtering can be implemented using a DNS layer.

Advantages include:

- ad blocking across all devices
- protection from known malware domains
- reduced tracking

---

# Internal DNS Namespaces

Creating a private domain namespace allows infrastructure to be addressed by name.

Example:

```
dns.lab.frost.vip
```

instead of

```
192.168.0.179
```

This improves usability and scalability.

---

# VPN-Based Remote Access

Using Tailscale allowed remote access without:

- port forwarding
- public exposure of services
- complex firewall configuration

The VPN overlay network simplifies connectivity while maintaining strong encryption.

---

# Infrastructure Documentation

Documenting the system architecture and configuration improves maintainability and reproducibility.

This project reinforced the importance of clear infrastructure documentation.