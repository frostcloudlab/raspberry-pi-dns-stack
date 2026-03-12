# Unbound Recursive DNS Resolver

Unbound is a local recursive DNS resolver.

It resolves DNS queries directly from root DNS servers.

---

# Benefits

- improved privacy
- no dependency on public DNS providers
- local caching
- faster repeated lookups

---

# Listening Port

```
5335
```

---

# Query Flow

Client Device  
→ AdGuard Home  
→ Unbound  
→ Root DNS Servers