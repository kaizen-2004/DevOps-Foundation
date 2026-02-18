# 2) Networking (Cloud-relevant)

## 2.1 DNS, HTTP/HTTPS, TLS basics

### Good looks like

You can debug “site down” without guessing.

### Concepts

- DNS: A/AAAA/CNAME, TTL

- HTTP vs HTTPS, status codes (200/301/403/404/500/502/504)

- TLS: cert mismatch, expired cert, SNI basics (concept-level)

### Labs

- Use `curl -I` to check headers/status

- Use `dig` to confirm correct record

- Simulate:
  - wrong DNS → NXDOMAIN

  - wrong port → timeout/refused

  - app error → 500

**Measurable outcomes**

- ✅ You can classify failures into: DNS / TCP / TLS / HTTP / app

---

## 2.2 Subnets + routing (private/public, NAT vs IGW)

### What you must understand (cloud transferable)

- **Public subnet**: has route to **Internet Gateway**

- **Private subnet**: no direct IGW route; uses **NAT** for outbound only

- Route tables decide _where traffic goes_

- Default route `0.0.0.0/0` is the “send to internet” decision

### Mini-diagram mental model

`Public subnet -> IGW -> Internet Private subnet -> NAT -> IGW -> Internet (outbound only)`

### Lab (even before AWS)

- On your VM, simulate “private” by blocking inbound ports and allowing outbound

- Practice recognizing “inbound blocked” vs “routing broken”

**Measurable outcomes**

- ✅ You can explain NAT vs IGW in 3–5 sentences clearly

- ✅ You can predict whether something is reachable from the internet

---

## 2.3 Firewalls / Security groups concepts

### Transferable idea

- **Security group** = instance-level “allow rules” (stateful concept)

- Network ACL = subnet-level rules (concept)

- Common result of misconfig: **timeouts** or “connection refused”

### Lab drill

- Run a service on port 8080

- Block it (local firewall or VM rules)

- Use `ss` and `curl -v` to prove:
  - service is listening but network blocks it

**Measurable outcomes**

- ✅ You can distinguish: “service not running” vs “blocked by firewall”

---

## 2.4 Common failure patterns to memorize

- **DNS misconfig** → `dig` fails / wrong target

- **Blocked ports** → timeout/refused

- **Wrong routes** → unreachable/timeout

- **TLS/cert issues** → handshake error in `curl -v`

- **App up but unhealthy behind LB** → 502/504 patterns

Make a one-page “Failure Pattern Cheat Sheet” in your repo.
