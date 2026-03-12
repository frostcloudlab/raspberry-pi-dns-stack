# DNS Infrastructure Architecture

This project implements a layered DNS architecture similar to those used in enterprise environments.

---

# High Level Design

User Device  
→ DNS Filter Layer  
→ Recursive Resolver Layer  
→ Internet Root DNS

---

# DNS Resolution Flow

Step 1

A device sends a DNS request to the network DNS server.

Example:

```
example.com
```

---

Step 2

AdGuard receives the query.

AdGuard checks:

- blocklists
- custom DNS rules
- local DNS records

If the domain is blocked, the request stops here.

---

Step 3

If the domain is allowed, AdGuard forwards the request to Unbound.

---

Step 4

Unbound performs recursive DNS resolution.

It queries the DNS hierarchy:

```
Root Servers
→ TLD Servers
→ Authoritative Servers
```

---

Step 5

The result is returned to AdGuard and then to the client.

---

# Remote Access Architecture

Remote devices connect using Tailscale.

This creates a secure private network between devices.

Remote Device  
→ Tailscale  
→ Raspberry Pi  
→ Home LAN

The Raspberry Pi advertises the subnet route:

```
192.168.0.0/24
```

This allows tailnet devices to access internal systems.

---

# Why This Architecture

Advantages:

- DNS privacy
- improved performance via caching
- centralized filtering
- secure remote access
- scalable internal DNS structure
