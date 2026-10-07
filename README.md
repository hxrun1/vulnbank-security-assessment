# VulnBank Mobile Banking Application — Security Assessment

A portfolio-ready copy of a mobile banking application security assessment performed against **VulnBank (`vulnbank3.apk`)**.

> **Public release note:** This repository contains a sanitized portfolio version of the assessment. Personal contact details, engagement credentials, and embedded screenshots have been removed or replaced.

## Assessment Overview

The assessment used a black-box approach and focused on identifying security weaknesses in the VulnBank mobile banking application and associated API functionality.

### Tools and Technologies

- Burp Suite
- MobSF
- Genymotion Emulator
- apktools
- Android application testing
- Manual API/security testing

## Key Findings

| ID | Finding | Severity |
|---|---|---|
| F1 | Transacting with a Negative Amount | Critical |
| F2 | Systemic Broken Access Control | Critical |
| F3 | Unauthorized Balance Check and Account Lookup | Critical |

### F1 — Negative Transaction Amount

The transfer functionality accepted a negative transaction amount. The recommended remediation is strict server-side validation requiring transaction amounts to be greater than zero, together with boundary-value testing.

### F2 — Systemic Broken Access Control

Client-supplied account identifiers could be manipulated to access resources belonging to other users. The recommended remediation is centralized, server-side authorization based on the authenticated user's identity and permitted account relationships.

### F3 — Unauthorized Balance Check and Account Lookup

Account identifiers exposed through debug functionality could be used to retrieve balance information for other accounts. The recommended remediation is to remove or restrict debug endpoints, enforce authentication and authorization, and prevent account enumeration.

## Repository Structure

```text
vulnbank-security-assessment/
├── README.md
├── .gitignore
├── report/
│   └── VulnBank_Mobile_Banking_Security_Assessment_Public.docx
└── methodology/
    └── assessment-notes.md
```

## Scope

The assessed application was:

```text
vulnbank3.apk
```

The public version intentionally does not include real credentials, passwords, tokens, certificates, or screenshots.

## Methodology

1. Passive information gathering
2. Active enumeration
3. Vulnerability scanning
4. Manual testing and validation
5. Risk assessment
6. Remediation recommendations
7. Retesting recommendations

## Disclaimer

This repository is provided for cybersecurity learning and portfolio purposes. Testing should only be performed against applications and systems where you have explicit authorization.
