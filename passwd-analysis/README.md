# Passwd File Analysis
## User, UID and Shell Inspection

---

## Context

The `/etc/passwd` file is a core Linux file containing user account information. While it does not store passwords, it is frequently used during security assessments to identify valid users, service accounts, and potential login vectors.

---

## Objective

Filter and extract specific information from `/etc/passwd` to identify:
- valid users
- associated UIDs
- configured shells
- non-interactive accounts

---

## Exercises Performed

The following tasks were completed using standard CLI tools:

1. Identify a specific user entry
2. Extract all usernames
3. Extract username and UID
4. Format output using custom delimiters
5. Include login shell information
6. Identify all valid login users
7. Exclude non-interactive accounts (`nologin`, `false`)
8. Count valid user accounts accurately


---

## Validation Approach

Tools used:
- `grep`
- `cut`
- `sed`
- `wc`

Example workflow:
```bash
cut -d: -f1,3,7 /etc/passwd | grep -Ev 'false|nologin' | sed 's/:/,/g'
```

Key Takeaways

/etc/passwd provides account metadata, not authentication data

Non-interactive users must be excluded during login analysis

Output formatting and normalization are required before counting

Incorrect assumptions lead to misleading metrics

Blue Team Relevance

User enumeration during incident response

Detection of unexpected interactive accounts

Validation of system hardening measures

