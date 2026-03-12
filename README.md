# Raspberry Pi DNS Stack

Self-hosted DNS and network services stack built on Raspberry Pi for home lab infrastructure.

## Project Status

Active home lab project.

This stack currently serves as the primary DNS server for my home network. The documentation will evolve as new services are added.

## Overview

This project documents my Raspberry Pi based DNS stack used as the primary DNS service for my home network. It is designed to improve visibility, privacy, and control over network traffic while also serving as a hands-on infrastructure lab.

## Core Components

- AdGuard Home for network-wide DNS filtering
- Unbound for recursive DNS resolution
- Tailscale for secure remote access
- Raspberry Pi as the host platform

## Project Goals

- Route home network DNS through the Pi
- Improve privacy and visibility
- Build practical Linux and networking experience
- Document the stack like a real infrastructure project

## Documentation

- [Architecture](docs/architecture.md)
- [Network Overview](docs/network-overview.md)
- [Hardware](docs/hardware.md)
- [AdGuard Home](docs/adguard.md)
- [Unbound](docs/unbound.md)
- [Tailscale](docs/tailscale.md)
- [DNS Configuration](docs/dns-configuration.md)
- [Future Improvements](docs/future-improvements.md)
- [Lessons Learned](docs/lessons-learned.md)

## Diagram

- [Network Diagram Notes](diagrams/network-diagram.md)

## Future Plans

Planned improvements include Wazuh, NAS-based storage, expanded monitoring, and continued integration with my broader Frost Cloud Lab environment.
