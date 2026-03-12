# Private Recursive DNS Infrastructure

This project documents the design and deployment of a private DNS infrastructure built for my homelab.

The system provides:

- Network-wide ad blocking
- Private recursive DNS resolution
- Internal DNS namespace
- Secure remote access to the home network
- Subnet routing via a private VPN

The infrastructure runs on a Raspberry Pi and mirrors many patterns used in production environments.

---

# Goals

The project was designed to accomplish several goals:

- Learn DNS infrastructure and recursive resolution
- Remove reliance on third-party DNS providers
- Provide ad and tracker blocking for all devices
- Build a secure remote access solution
- Create an internal DNS namespace for future services

---

# System Architecture

Client Device  
→ AdGuard DNS Filter  
→ Unbound Recursive Resolver  
→ Root DNS Servers

Remote devices access the network through Tailscale.

Remote Device  
→ Tailscale VPN  
→ Raspberry Pi  
→ Home LAN

---

# Key Components

## Raspberry Pi 4

Acts as the infrastructure node for the lab.

Responsibilities:

- DNS server
- ad blocking
- recursive DNS resolution
- internal DNS authority
- VPN access point
- subnet router

---

## AdGuard Home

AdGuard Home acts as the primary DNS server for the network.

Responsibilities:

- DNS filtering
- ad and tracker blocking
- malware domain blocking
- custom DNS records
- web-based management dashboard

---

## Unbound

Unbound provides recursive DNS resolution.

Instead of forwarding requests to public DNS providers such as Google or Cloudflare, Unbound queries root DNS servers directly.

Advantages:

- improved privacy
- no third-party DNS dependency
- local caching
- faster repeated queries

---

## Tailscale

Tailscale provides secure remote access to the network.

Features used:

- encrypted VPN connectivity
- subnet routing
- remote SSH access
- access to internal services without port forwarding

---

# Internal DNS Namespace

The lab uses an internal DNS namespace:

```
lab.frost.vip
```

Example records:

```
dns.lab.frost.vip
router.lab.frost.vip
compute.lab.frost.vip
```

This allows services to be addressed by name instead of IP.

---

# Network Layout

LAN network:

```
192.168.0.0/24
```

Key hosts:

```
192.168.0.1   Router
192.168.0.179 Raspberry Pi DNS server
```

---

# Ports Used

```
53    DNS (AdGuard)
5335  Unbound recursive resolver
80    AdGuard web interface
22    SSH
```

---

# Privacy Benefits

This architecture improves privacy compared to standard home networks.

Advantages:

- DNS queries resolved locally
- no dependency on Google or Cloudflare DNS
- network-wide ad blocking
- encrypted remote access

---

# Future Improvements

Planned improvements include:

- dedicated compute server
- containerized services
- reverse proxy with automatic TLS
- monitoring stack
- infrastructure automation
- central security monitoring platform (SIEM)
