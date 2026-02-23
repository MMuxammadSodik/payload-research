# Privilege Escalation Research

## Overview

This directory contains structured research, notes, and exploitation references related to privilege escalation techniques across different operating systems.

The objective is to document misconfigurations, vulnerable services, weak permissions, and post-exploitation pathways that allow escalation from a low-privileged user to administrative or root-level access.

This research is organized by platform and focuses on practical enumeration methodology, exploitation logic, and defensive weaknesses commonly observed in real-world systems and lab environments.

Platforms:

- Windows
- Linux

---

## Platforms Covered

### Windows

Research under the Windows section includes:

- Misconfigured services (unquoted service paths, weak service permissions)
- Insecure registry permissions
- Token impersonation (e.g., SeImpersonatePrivilege abuse)
- Scheduled task misconfigurations
- Weak folder/file ACLs
- DLL hijacking opportunities
- Credential harvesting vectors
- AlwaysInstallElevated misconfiguration
- Service account abuse
- Privileged group misconfigurations

The focus is on understanding Windows security architecture, access control mechanisms, and privilege boundaries.

---

### Linux

Research under the Linux section includes:

- SUID/SGID binaries and abuse patterns
- Writable service configurations
- Cron job misconfigurations
- PATH hijacking
- Capability-based privilege escalation
- Kernel exploit research 
- Weak file and directory permissions
- NFS misconfigurations
- Environment variable abuse
- Misconfigured sudo rules

The emphasis is on enumeration methodology, permission models, and common administrative mistakes that introduce privilege escalation vectors.
