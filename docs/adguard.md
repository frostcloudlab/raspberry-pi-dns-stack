# AdGuard Home

AdGuard Home provides DNS filtering and ad blocking for the entire network.

---

# Responsibilities

- DNS resolution for clients
- domain blocking
- malware domain protection
- custom DNS records

---

# Listening Port

```
53
```

---

# Web Interface

```
http://dns.lab.frost.vip
http://adguard.lab.frost.vip
```

or

```
http://192.168.0.179
```

---

# Upstream Resolver

AdGuard forwards queries to:

```
Unbound
```

running locally on the Raspberry Pi.