# 1) Linux (Ops-level)

## 1.1 Processes & services (systemd, journalctl)

### Good looks like

You can answer in minutes:

- “Why is my service down?”

- “What changed?”

- “How do I safely restart without guessing?”

### Concepts

- Process vs service

- Exit codes (0 success; non-zero fail)

- `systemd` units, `ExecStart`, dependencies

- Logs via `journalctl`

### Must-know commands

- Services:
  - `systemctl status <service>`

  - `systemctl start|stop|restart <service>`

  - `systemctl enable|disable <service>`

- Logs:
  - `journalctl -u <service> -n 200 --no-pager`

  - `journalctl -u <service> --since "1 hour ago"`

- Processes:
  - `ps aux | grep <name>`

  - `top` / `htop`

  - `kill -SIGTERM <pid>` then `kill -9 <pid>` (last resort)

### Mini-lab: “Hello Service”

1. Create a simple script that prints something every 2 seconds.

2. Create a systemd service for it.

3. Intentionally break it (bad path, wrong perms), then fix it.

**Measurable outcomes**

- ✅ You can `systemctl start` and see logs in `journalctl`

- ✅ You can explain what the unit file does

- ✅ You can diagnose a failed start from logs

### Common failures to drill

- Wrong file permissions (`Permission denied`)

- Missing environment variables

- Wrong working directory

- Port already in use

**Portfolio writeup**

- A 1-page runbook: _“How I debug a failed systemd service”_

---

## 1.2 Logs (locations, levels, rotation basics)

### Good looks like

You can locate logs fast and decide what matters.

### Concepts

- Common log paths:
  - `/var/log/syslog` (Ubuntu/Debian)

  - `/var/log/auth.log`

  - Application logs (varies)

- Log levels: DEBUG/INFO/WARN/ERROR

- Rotation (you don’t need to master, just understand):
  - `logrotate`, rotated files like `.1`, `.gz`

### Must-know commands

- `tail -f /var/log/syslog`

- `grep -R "ERROR" /var/log/`

- `less <file>`

- `zless /var/log/<rotated>.gz`

### Mini-lab: “Log hunting”

- Generate logs (failed SSH attempt, service failure)

- Find the exact lines proving what happened

**Measurable outcomes**

- ✅ You can find auth-related events in `auth.log`

- ✅ You can explain “what happened” using log evidence

---

## 1.3 Permissions (users/groups/sudo/SSH keys)

### Good looks like

You can fix access problems without random chmod-ing.

### Concepts

- Users/groups ownership: `user:group`

- Permissions: `rwx` for user/group/other

- `sudo` policy basics (least privilege mentality)

- SSH keys: private key, public key, `authorized_keys`

### Must-know commands

- `ls -lah`

- `id`, `groups`

- `chmod`, `chown`

- `sudo -l`

- SSH:
  - `ssh -i key.pem user@host`

  - `~/.ssh/config` (quality-of-life)

### Mini-lab: “Permission denied”

- Create a folder a new user can’t read

- Fix it _properly_ using group ownership or intended perms

- Set up key-based SSH login (on your VM)

**Measurable outcomes**

- ✅ You can explain why access failed (owner/group/other)

- ✅ You can fix it with minimal permission changes

- ✅ You can SSH with keys reliably

---

## 1.4 Networking tools (curl, dig, ss, traceroute, tcpdump)

### Good looks like

You can isolate “network problem” into DNS vs routing vs firewall vs app.

### Must-know commands + what they prove

- `curl -v http://host:port` → app reachability + HTTP status + TLS

- `dig example.com` / `nslookup` → DNS correctness

- `ss -tulpn` → what’s listening on ports (server-side truth)

- `traceroute host` → path/routing issues (high-level)

- `tcpdump -i eth0 port 80` → proof packets arrive/leave (basic)

### Mini-lab: “Is it DNS or the app?”

- Run a local web service

- Break DNS resolution or hosts mapping

- Use tools to prove the root cause

**Measurable outcomes**

- ✅ You can prove where failure occurs (DNS vs port vs service)

---

## 1.5 Troubleshooting playbook (your default method)

### Template

1. **Symptom:** what is broken? who is impacted?

2. **Hypothesis:** 2–3 likely causes

3. **Test:** quick checks to confirm/deny each

4. **Fix:** smallest safe change

5. **Prevent:** monitoring, automation, documentation

### Practice drill (repeat weekly)

Pick one:

- service down

- port blocked

- wrong config

- permission denied
  …and write a 10–15 line incident note using the template.

**Measurable outcome**

- ✅ 5 incident notes in your repo by graduation
