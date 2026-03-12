# Architecture

This project runs a lightweight DNS infrastructure stack on a Raspberry Pi that serves as the primary DNS server for the home network.

The stack provides DNS filtering, recursive resolution, and secure remote administration.

## Core Components

### Raspberry Pi

The Raspberry Pi hosts the DNS services for the network. It runs multiple services that work together to process DNS queries and provide secure management access.

Services running on the Pi:

- AdGuard Home
- Unbound
- Tailscale

### AdGuard Home

AdGuard Home is the primary DNS interface for the network.

Responsibilities:

- Network-wide DNS filtering
- Query logging and visibility
- DNS request handling for client devices
- Forwarding upstream queries to Unbound

All DNS requests from client devices are first processed by AdGuard.

### Unbound

Unbound provides recursive DNS resolution.

Instead of forwarding requests to public DNS providers, Unbound resolves domains directly from the DNS root servers.

Benefits include:

- Improved privacy
- Reduced reliance on third-party DNS providers
- More control over DNS resolution

### Tailscale

Tailscale provides secure remote access to the Raspberry Pi and other devices in the lab.

The Raspberry Pi joins a private tailnet alongside trusted devices such as laptops and phones.

This allows:

- Remote administration of the Pi
- Access to the AdGuard dashboard
- Secure SSH access

No services are exposed directly to the public internet.

## DNS Resolution Flow

DNS queries follow this path:

1. Client device sends DNS request
2. Request reaches AdGuard Home on the Raspberry Pi
3. AdGuard applies filtering and logging
4. AdGuard forwards the query to Unbound
5. Unbound performs recursive resolution
6. Response returns to the client device
