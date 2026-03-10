# Payload Research

Curated payload collection for **web vulnerabilities** and **privilege escalation** techniques used in penetration testing, CTF challenges, and security research.

---

# Navigation

## Privilege Escalation

- [Linux](#linux)
  - [CronJob Abuse](#cronjob-abuse)
  - [WildCard Abuse](#wildcard-abuse)
  - [Environment Attacks](#environment-attacks)
  - [Service Attacks](#service-attacks)

- [Windows](#windows)
  - [User Privileges](#user-privileges)
  - [Group Privileges](#group-privileges)
  - [OS Attacks](#os-attacks)
  - [Credential Hunting](#credential-hunting)
  - [Windows DLL Hijacking](#windows-dll-hijacking)

---

# Privilege Escalation

## Linux

### CronJob Abuse

Payloads related to exploiting misconfigured cron jobs.

---

### WildCard Abuse

Payloads abusing wildcard expansion in commands like `tar`, `rsync`, etc.

---

### Environment Attacks

Techniques abusing environment variables and PATH misconfigurations.

---

### Service Attacks

Payloads targeting writable or misconfigured services.

---

## Windows

### User Privileges

Payloads leveraging dangerous user privileges such as:

- `SeImpersonatePrivilege`
- `SeBackupPrivilege`
- `SeRestorePrivilege`

---

### Group Privileges

Abusing group memberships for privilege escalation.

---

### OS Attacks

Techniques targeting operating system misconfigurations.

---

### Credential Hunting

Payloads used to locate credentials in:

- registry
- configuration files
- memory
- cached credentials

---

### Windows DLL Hijacking

Payloads exploiting DLL search order hijacking vulnerabilities.

---

# Disclaimer

This repository is intended **for educational purposes and authorized security testing only**.

The author assumes **no responsibility for misuse** of the information provided.

Always ensure you have **explicit permission** before testing systems.

---

# License

MIT License
