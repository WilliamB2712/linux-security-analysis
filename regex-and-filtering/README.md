Regex and Filtering Practice

SSH Configuration Analysis

---

## Context

Regex is a critical skill for filtering logs and configuration files during security investigations. This exercise focused on applying regex patterns to real configuration data.

The target file used was:
/etc/ssh/sshd_config

yaml
Copiar código

---

## Objective

Practice identifying security-relevant configuration entries using regex-based filtering.

---

## Tasks Performed

1. Display lines that do not contain comments
2. Match directives starting with `Permit`
3. Identify authentication-related directives
4. Search for key-related settings
5. Match password authentication rules
6. Identify configuration lines ending in `yes`

---

## Example Commands

```bash
grep -v '^#' sshd_config
grep -E '^Permit' sshd_config
grep -E 'Authentication$' sshd_config
grep -E 'Key' sshd_config
grep -E '^Password.*yes' sshd_config
grep -E 'yes$' sshd_config
```

---

## Key Takeaways
Regex allows precise extraction of configuration intent

Anchors (^, $) reduce false positives

Filtering commented lines is essential for accurate analysis

Regex is foundational for log analysis and detection rules

## Blue Team Relevance
SSH hardening verification

Configuration drift detection

Log and config triage

SOC-level investigation workflows
