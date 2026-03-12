# Network Diagram

This document visualizes how DNS traffic flows through the Raspberry Pi DNS stack both inside the home network and through secure remote access.

## Internal Network DNS Flow

This diagram shows how devices on the home network use the Raspberry Pi as their DNS server.

The Raspberry Pi acts as the DNS hub for the LAN. Client devices send DNS requests to the Pi, which processes them through AdGuard and Unbound before forwarding upstream queries to the router and then the internet.

```text
        ┌──────────────────────────────────┐
        │             Home LAN             │
        │                                  │
        │  Laptop      Phone      TV       │
        │     │           │        │       │
        │     │           │        │       │
        │     └───────┬───┴───┬────┘       │
        │             │       │            │
        │             ▼       ▼            │
        │        ┌────────────────┐        │
        │        │  Raspberry Pi  │        │
        │        │   DNS Server   │        │
        │        │                │        │
        │        │  AdGuard Home  │        │
        │        │  DNS Filtering │        │
        │        │        │       │        │
        │        │        ▼       │        │
        │        │     Unbound    │        │
        │        │ Recursive DNS  │        │
        │        └────────┬───────┘        │
        │                 │                │
        │          Upstream Queries       │
        │                 │                │
        └─────────────────┼────────────────┘
                          │
                          ▼
                     Home Router
                  (Gateway + DHCP)
                          │
                          ▼
                       Internet
```

## External Remote Access Flow

This diagram shows how trusted devices outside the home network securely access the Raspberry Pi using Tailscale.

Remote devices join the same private tailnet as the Raspberry Pi. The encrypted tunnel allows access to the Pi and other lab resources without exposing services to the public internet.

```text
        Remote Laptop / Phone
                │
                │
             Internet
                │
                │
        Encrypted Tailscale Tunnel
                │
                ▼
        ┌──────────────────────────────┐
        │           Home LAN           │
        │                              │
        │      ┌────────────────┐      │
        │      │  Raspberry Pi  │      │
        │      │   DNS Server   │      │
        │      │                │      │
        │      │   AdGuard      │      │
        │      │   Unbound      │      │
        │      │   Tailscale    │      │
        │      └────────┬───────┘      │
        │               │              │
        │     Access to lab services   │
        │               │              │
        │       ┌───────┴────────┐     │
        │       │ Other LAN      │     │
        │       │ Devices        │     │
        │       │ (optional)     │     │
        │       └────────────────┘     │
        │                              │
        └───────────────┬──────────────┘
                        │
                        ▼
                   Home Router
                (Gateway + DHCP)
                        │
                        ▼
                     Internet
```

## Design Principles

This architecture is designed around a few simple principles:

**Centralized DNS**

All devices on the home network send DNS queries to the Raspberry Pi. This provides a single point for filtering, monitoring, and DNS resolution.

**Privacy-Focused Resolution**

DNS requests are resolved through Unbound using recursive resolution rather than relying on public DNS providers.

**Secure Remote Management**

Administrative access to the Raspberry Pi is provided through Tailscale. This allows trusted devices to access the lab environment without exposing services directly to the public internet.

**Minimal Infrastructure**

The Raspberry Pi acts as a lightweight infrastructure host for multiple services while keeping the overall network design simple.

## Diagram Notes

The ASCII diagrams in this document represent the logical architecture of the system.  
A graphical version of the network diagram will be included in the repository:

`images/network-diagram.png`

The graphical diagram provides a clearer visualization of the relationships between:

- client devices
- the Raspberry Pi DNS stack
- the home router
- external access through Tailscale