# Tailscale VPN

Tailscale provides secure remote access to the homelab network.

---

# Features Used

- encrypted VPN
- remote SSH access
- subnet routing

---

# Subnet Route

The Raspberry Pi advertises:

```
192.168.0.0/24
```

This allows tailnet devices to access the entire home LAN.

---

# Example Access

Remote device connected to Tailscale can reach:

```
192.168.0.179
router.lab.frost.vip
dns.lab.frost.vip
```