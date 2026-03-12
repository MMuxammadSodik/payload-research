# Payload Research

Curated payload collection for **web vulnerabilities** and **privilege escalation** techniques used in penetration testing, CTF challenges, and security research.

---

# Navigation

- [Web Vulnerabilities](#web-vulnerabilities)
- [Privilege Escalation](#privilege-escalation)

## Privilege Escalation

 - [Linux](#linux)
   - [SUID Binaries](#suid-binaries)
   - [Sudo Misconfiguration](#sudo-misconfiguration)
   - [Capabilities Abuse](#capabilities-abuse)
   - [Writable Files](#writable-files)
   - [NFS Misconfiguration](#nfs-misconfiguration)
   - [Kernel Exploits](#kernel-exploits)
   - [Docker / Container Escape](#docker--container-escape)
   - [LD_PRELOAD Abuse](#ld_preload-abuse)

 - [Windows](#windows)
   - [Unquoted Service Paths](#unquoted-service-paths)
   - [Weak Service Permissions](#weak-service-permissions)
   - [Scheduled Task Abuse](#scheduled-task-abuse)
   - [AlwaysInstallElevated](#alwaysinstallelevated)
   - [Token Impersonation](#token-impersonation)
   - [UAC Bypass](#uac-bypass)
   - [PATH Hijacking](#path-hijacking)
   - [Registry Misconfiguration](#registry-misconfiguration)

## Web Vulnerabilities

- [Cross-Site Scripting (XSS)](#cross-site-scripting-xss)
- [SQL Injection (SQLi)](#sql-injection-sqli)
- [Cross-Site Request Forgery (CSRF)](#cross-site-request-forgery-csrf)
- [Server-Side Request Forgery (SSRF)](#server-side-request-forgery-ssrf)
- [Local File Inclusion (LFI)](#local-file-inclusion-lfi)
- [Remote File Inclusion (RFI)](#remote-file-inclusion-rfi)
- [Command Injection](#command-injection)
- [Open Redirect](#open-redirect)
- [Insecure Direct Object Reference (IDOR)](#insecure-direct-object-reference-idor)
- [File Upload Vulnerabilities](#file-upload-vulnerabilities)
- [XML External Entity (XXE)](#xml-external-entity-xxe)
- [Server-Side Template Injection (SSTI)](#server-side-template-injection-ssti)
- [Business Logic Vulnerabilities](#business-logic-vulnerabilities)
- [HTTP Request Smuggling](#http-request-smuggling)
- [HTTP Parameter Pollution (HPP)](#http-parameter-pollution-hpp)
- [Clickjacking](#clickjacking)
- [Web Cache Poisoning](#web-cache-poisoning)
- [Host Header Injection](#host-header-injection)
- [JWT Vulnerabilities](#jwt-vulnerabilities)
- [CORS Misconfiguration](#cors-misconfiguration)
- [Race Conditions](#race-conditions)
  
---

# Web Vulnerabilities

## Cross-Site Scripting (XSS)

Payloads related to injecting malicious scripts into web pages viewed by other users.

Types include:

- Reflected XSS
- Stored XSS
- DOM-Based XSS
- Blind XSS

---

## SQL Injection (SQLi)

Payloads exploiting unsanitized SQL queries to manipulate database operations.

Types include:

- Union-based SQLi
- Error-based SQLi
- Boolean-based blind SQLi
- Time-based blind SQLi
- Out-of-band SQLi

---

## Cross-Site Request Forgery (CSRF)

Payloads forcing authenticated users to perform unintended actions on a web application.

Common targets:

- password changes
- email updates
- financial transactions

---

## Server-Side Request Forgery (SSRF)

Payloads forcing the server to make requests to unintended internal or external resources.

Common targets:

- internal services
- cloud metadata endpoints
- internal APIs

---

## Local File Inclusion (LFI)

Payloads used to include files from the local server filesystem.

Common targets:

- `/etc/passwd`
- log files
- configuration files

---

## Remote File Inclusion (RFI)

Payloads that cause the application to include remote files from external servers.

Often leads to **remote code execution**.

---

## Command Injection

Payloads exploiting applications that pass unsanitized input to system shell commands.

Targets include:

- system utilities
- script interpreters
- OS commands

---

## Open Redirect

Payloads manipulating redirect parameters to send users to malicious websites.

Common exploitation scenarios:

- phishing
- token leakage

---

## Insecure Direct Object Reference (IDOR)

Payloads manipulating object identifiers to access unauthorized resources.

Common targets:

- user IDs
- order IDs
- document IDs
- API object references

---

## File Upload Vulnerabilities

Payloads exploiting insecure file upload mechanisms.

Common techniques:

- webshell uploads
- extension bypass
- MIME-type bypass
- double extensions

---

## XML External Entity (XXE)

Payloads exploiting XML parsers that allow external entity processing.

Potential impacts:

- file disclosure
- SSRF
- remote code execution

---

## Server-Side Template Injection (SSTI)

Payloads exploiting template engines that evaluate user input.

Common template engines:

- Jinja2
- Twig
- Freemarker
- Velocity

---

## Business Logic Vulnerabilities

Payloads abusing flaws in application logic rather than technical vulnerabilities.

Examples include:

- price manipulation
- workflow bypass
- coupon abuse

---

## HTTP Request Smuggling

Payloads exploiting inconsistencies between front-end and back-end HTTP parsers.

Common techniques:

- CL.TE
- TE.CL
- TE.TE

---

## HTTP Parameter Pollution (HPP)

Payloads exploiting how applications handle duplicated HTTP parameters.

Can lead to:

- authentication bypass
- filter bypass
- WAF bypass

---

## Clickjacking

Payloads exploiting UI redressing attacks using iframes.

Common goal:

- tricking users into clicking hidden actions.

---

## Web Cache Poisoning

Payloads manipulating caching behavior to serve malicious responses to other users.

Targets include:

- reverse proxies
- CDNs
- application caches

---

## Host Header Injection

Payloads manipulating the `Host` header to exploit insecure server logic.

Common impacts:

- password reset poisoning
- cache poisoning
- routing manipulation

---

## JWT Vulnerabilities

Payloads targeting insecure JSON Web Token implementations.

Common issues:

- algorithm confusion
- weak secrets
- missing signature verification

---

## CORS Misconfiguration

Payloads exploiting overly permissive Cross-Origin Resource Sharing policies.

Common impacts:

- sensitive data leakage
- account takeover

---

## Race Conditions

Payloads exploiting timing issues where multiple requests cause inconsistent application state.

Common targets:

- payment systems
- registration systems
- coupon redemption


# Privilege Escalation

## Linux

### SUID Binaries

Payloads exploiting binaries with the **SUID bit** set that execute with elevated privileges.

Common abuse involves:

- misconfigured system binaries
- custom SUID programs
- GTFOBins techniques

---

### Sudo Misconfiguration

Payloads targeting insecure **sudo rules**.

Common scenarios include:

- `NOPASSWD` misconfiguration
- running dangerous binaries as root
- wildcard abuse

---

### Capabilities Abuse

Payloads exploiting Linux **file capabilities** that allow privileged actions without full root.

Common capability abuses include:

- `cap_setuid`
- `cap_dac_read_search`
- `cap_sys_admin`

---

### Writable Files

Payloads targeting **world-writable files** or configuration files that influence privileged processes.

Examples include:

- service configuration files
- scripts executed by root
- system startup files

---

### NFS Misconfiguration

Payloads abusing improperly configured **NFS shares**.

Typical issues include:

- `no_root_squash`
- writable shared directories

---

### Kernel Exploits

Payloads leveraging vulnerable Linux kernels to escalate privileges.

Often involves:

- public kernel exploits
- outdated kernel versions
- misconfigured security modules

---

### Docker / Container Escape

Payloads used to escape containerized environments.

Common targets include:

- mounted Docker socket
- privileged containers
- writable host mounts

---

### LD_PRELOAD Abuse

Payloads exploiting the `LD_PRELOAD` environment variable to load malicious shared libraries.

Often possible when:

- running sudo commands
- vulnerable service execution

## Windows

### Unquoted Service Paths

Payloads exploiting Windows services with **unquoted executable paths**.

Attackers can place malicious executables in writable directories along the path.

---

### Weak Service Permissions

Payloads abusing services where users can:

- modify service binaries
- restart services
- change service configuration

---

### Scheduled Task Abuse

Payloads exploiting misconfigured Windows scheduled tasks.

Common issues include:

- writable task executables
- tasks running as SYSTEM

---

### AlwaysInstallElevated

Payloads exploiting the Windows **AlwaysInstallElevated** policy.

Allows low-privileged users to install MSI packages with SYSTEM privileges.

---

### Token Impersonation

Payloads exploiting privileged tokens to impersonate higher-privileged users.

Commonly abused privileges:

- `SeImpersonatePrivilege`
- `SeAssignPrimaryTokenPrivilege`

---

### UAC Bypass

Payloads exploiting techniques that bypass **User Account Control** protections.

Common methods include:

- auto-elevated binaries
- registry hijacking
- COM interface abuse

---

### PATH Hijacking

Payloads exploiting insecure search paths used by privileged applications.

Attackers place malicious binaries in directories that appear earlier in the PATH.

---

### Registry Misconfiguration

Payloads exploiting insecure registry permissions.

Targets include:

- startup registry keys
- service registry configurations

# Disclaimer

This repository is intended **for educational purposes and authorized security testing only**.

The author assumes **no responsibility for misuse** of the information provided.

Always ensure you have **explicit permission** before testing systems.

---

# License

MIT License
