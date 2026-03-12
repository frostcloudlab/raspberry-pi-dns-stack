# Network Overview

The Raspberry Pi DNS stack serves as the primary DNS infrastructure for the home network.

All devices on the local network send DNS queries to the Raspberry Pi, allowing centralized filtering, logging, and recursive DNS resolution.

## Network Roles

### Router / Gateway

The home router provides the following functions:

- Internet gateway
- DHCP address assignment
- Network routing

The router is configured so that the Raspberry Pi is used as the primary DNS server for the network.

### Raspberry Pi DNS Server

The Raspberry Pi acts as the DNS infrastructure node for the LAN.

It provides:

- DNS filtering through AdGuard Home
- Recursive DNS resolution via Unbound
- Remote administration through Tailscale

Because all devices use the Pi for DNS, the system provides a centralized point for monitoring and controlling DNS activity.

### Client Devices

Devices on the network that use the Raspberry Pi for DNS include:

- Desktop computers
- Laptops
- Mobile phones
- Streaming devices
- Game consoles
- Smart home devices

These devices automatically send DNS requests to the Pi through DHCP configuration from the router.

## Remote Access

Secure remote access to the lab is provided through Tailscale.

Devices connected to the tailnet include:

- Raspberry Pi
- Personal laptops
- Mobile phones

This allows the DNS stack to be managed remotely without exposing services to the public internet.

## Design Goals

This architecture is designed to:

- Centralize DNS control within the home network
- Improve visibility into DNS activity
- Increase privacy by using recursive DNS resolution
- Provide hands-on infrastructure experience for homelab development
