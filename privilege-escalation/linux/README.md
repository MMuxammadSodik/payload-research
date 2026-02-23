# Linux Privilege Escalation

This repository documents common Linux local privilege escalation techniques
encountered during penetration tests, red team engagements, and security research.

The focus is on understanding exploitation conditions, identifying
misconfigurations, and applying controlled privilege escalation techniques
within authorized environments.

---

## Scope

The techniques covered in this repository include, but are not limited to:

- PATH Abuse
- Wildcard Injection
- Cron Job Misconfiguration
- LXD Group Abuse
- Docker Group Abuse
- Kernel-Level Exploits
- Additional Misconfigurations & Edge Cases

Each technique is documented with practical exploitation context
and defensive considerations.

---

## Documentation Structure

Each technique directory contains:

### 1. Vulnerability Overview
- Technical explanation of the weakness
- Required preconditions
- Why the issue results in privilege escalation

### 2. Enumeration Indicators
- Commands used to identify exposure
- Configuration patterns to inspect
- Validation steps before exploitation

### 3. Exploitation Method
- Controlled proof-of-concept payloads
- Escalation workflow
- Operational considerations

### 4. Defensive Recommendations
- Hardening guidance
- Configuration corrections
- Principle of least privilege enforcement

## Intended Use

This repository is intended for:
- Penetration testers
- Red team operators
- Security researchers
- Defensive teams studying escalation vectors

All techniques must be used strictly within legally authorized environments.
Unauthorized use is unethical and potentially illegal.
