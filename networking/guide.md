# Networking Learning Plan

## Goal
Develop cloud-ready networking fundamentals so you can diagnose connectivity and service reachability issues quickly.

## Time Commitment
- 5 weeks
- 5 sessions per week
- 60 to 90 minutes per session

## Prerequisites
- Linux VM with internet access
- Tools installed: `curl`, `dig`, `ip`, `ss`, `traceroute`, `tcpdump`
- Basic comfort with terminal commands

## Week 1: Core TCP/IP and Packet Flow
### Focus
- OSI vs TCP/IP model (practical view)
- IP addresses, CIDR notation, subnets
- Packet flow from client to service

### Labs
1. Identify local IP, gateway, and DNS resolver.
2. Convert CIDR blocks to host ranges.
3. Draw packet path for one request in your notes.

### Done Criteria
- You can explain how a request travels from browser to server.
- You can calculate usable IP ranges from a CIDR block.

## Week 2: DNS, HTTP, HTTPS, TLS
### Focus
- DNS records (`A`, `AAAA`, `CNAME`) and TTL behavior
- HTTP response codes and request/response flow
- TLS handshake basics and certificate failures

### Labs
1. Use `dig` and `nslookup` to validate DNS records.
2. Use `curl -I` and `curl -v` to inspect status codes and TLS details.
3. Simulate wrong DNS and expired-cert scenarios in a lab setup.

### Done Criteria
- You can separate DNS issues from HTTP/TLS issues.
- You can read `curl -v` output and identify handshake failures.

## Week 3: Routing, NAT, Public vs Private Reachability
### Focus
- Route tables and default routes
- Public subnet vs private subnet behavior
- NAT for outbound-only internet access

### Labs
1. Inspect route tables with `ip route`.
2. Simulate blocked inbound and working outbound traffic.
3. Explain when Internet Gateway vs NAT is required in AWS.

### Done Criteria
- You can predict whether a host is internet-reachable.
- You can explain NAT vs Internet Gateway in practical terms.

## Week 4: Firewalls and Access Controls
### Focus
- Host firewall concepts (`ufw`/`iptables`/`nftables`)
- Security group mindset vs network ACL mindset
- Timeout vs connection refused patterns

### Labs
1. Run a service on port `8080`.
2. Block and unblock traffic at firewall level.
3. Use `ss`, `curl`, and logs to prove the exact failure point.

### Done Criteria
- You can distinguish "app down" from "network blocked".
- You can verify listening ports and allowed paths confidently.

## Week 5: Troubleshooting Patterns and Incident Drills
### Focus
- A repeatable triage workflow
- Common outage patterns and first checks
- Writing evidence-driven incident notes

### Labs
1. Run three timed drills:
   - DNS misconfiguration
   - Firewall block
   - Wrong upstream target
2. For each drill, write symptom, hypothesis, tests, fix, prevention.

### Final Project
Build a "Network Troubleshooting Playbook" including:
- Command checklist by failure type
- Decision tree (DNS vs routing vs firewall vs app)
- Three completed incident reports from your drills

## Mastery Checklist
- I can classify failures as DNS, TCP, TLS, HTTP, or app-layer.
- I can prove root cause with commands, not assumptions.
- I can explain public/private subnet behavior clearly.
