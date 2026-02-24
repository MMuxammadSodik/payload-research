# Payload Research

This repository contains **research notes and payloads** documented during
**Penetration Testing**.

This repository is **educational and research-oriented** and is not intended
for unauthorized or malicious use.

# All Techniques

- [Privilege-escalation](privilege-escalation/)
  - [Linux](privilege-escalation/Linux/)
    - [PATH Abuse](privilege-escalation/Linux/PATH_Abuse/)
    - [Wildcard Abuse](privilege-escalation/Linux/Wildcard_Abuse/)
    - [Cron Job Abuse](privilege-escalation/Linux/cron_abuse/)
    - [Docker](privilege-escalation/Linux/Docker/)
    - [LXD](privilege-escalation/Linux/LXD/)
    - [Kernel Exploits](privilege-escalation/Linux/Kernel_Exploits/)

---

## Purpose

The objectives of this repository are to:

- Understand how common vulnerabilities work in real applications
- Document exploitation techniques with proper context
- Record payload behavior, limitations, and observations
- Develop a repeatable methodology for penetration testing

Content is added **incrementally**, based on hands-on testing and validation.

---

## Scope

The repository focuses primarily on **web application vulnerabilities**, with
coverage expanding over time as techniques are studied and practiced.

Current and planned areas include:

- Web application vulnerabilities (e.g. Injection, Authentication issues)
- Technique-specific exploitation approaches
- Practical payloads tested in labs
- High-level defensive considerations


Each vulnerability or technique directory typically contains:
- A conceptual overview
- Technique-specific notes
- Practical payloads tested in labs
- Indicators, limitations, and observations
  
---

## Methodology

Documentation follows a **depth-first approach**:

- One vulnerability at a time
- One technique at a time
- Focus on understanding before expansion

---

## Standards & References

Where applicable, vulnerabilities are aligned with common industry references,
such as:

- OWASP Top 10
- Common real-world exploitation patterns

These references are used for learning alignment only.

---

## Legal & Ethical Notice

All content in this repository:

- Is created for educational and research purposes
- Is tested only in authorized lab environments
- Must not be used against systems without explicit permission

Unauthorized use of these techniques may be illegal and unethical.

---

## Disclaimer

This repository represents a **personal research notebook**.  
The presence or absence of specific vulnerabilities, techniques, or payloads
does not indicate expertise or lack thereof—only what has been documented so far.

The repository evolves continuously as learning progresses.
