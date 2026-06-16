# OWASP Top 10 Flask Security Lab

A hands-on OWASP Top 10 learning lab built with Python and Flask.

This repository focuses on secure coding, detection limits, CI validation, and understanding where human AppSec review is still required.

Each category contains intentionally vulnerable examples, secure implementations, walkthroughs, and notes on how the issue can be identified using automated tooling and manual review techniques.

## Goals

* Build practical familiarity with the OWASP Top 10.
* Demonstrate vulnerable and secure coding patterns side-by-side.
* Explore where SAST, DAST, SCA, secrets scanning, and other tooling provide value.
* Highlight categories that rely heavily on threat modeling and manual testing.
* Provide lightweight examples suitable for learning, experimentation, and AppSec discussions.

## Detection Coverage

The OWASP Top 10 includes categories that vary significantly in how effectively they can be identified through automated tooling. This matrix highlights where SAST, DAST, SCA, and human AppSec review are most valuable.

| Category | Examples | SAST | DAST | SCA | Manual Review |
|-----------|-----------|:----:|:----:|:---:|:--------------:|
| A01 Broken Access Control | Planned | ❌ | ⚠️ | ❌ | ✅ |
| A03 Injection | SQLi, XSS | ✅ | ✅ | ❌ | ✅ |
| A05 Security Misconfiguration | Planned | ⚠️ | ✅ | ❌ | ✅ |
| A06 Vulnerable Components | Planned | ❌ | ❌ | ✅ | ⚠️ |
| A07 Authentication Failures | CSRF | ⚠️ | ⚠️ | ❌ | ✅ |

**Legend:**
- ✅ Effective detection approach
- ⚠️ Partial coverage or situational effectiveness
- ❌ Generally ineffective for this category

## Security CI Pipeline

GitHub Actions security checks include:

* SAST (Semgrep)
* SCA (pip-audit)
* Secrets scanning (Gitleaks)
* DAST (OWASP ZAP Baseline Scan)

Pipeline flow:

1. Code is pushed or a pull request is opened.
2. Security scans execute automatically.
3. Blocking checks fail the pipeline when configured findings are detected.
4. Findings are reviewed and remediated before merge.
5. DAST artifacts are uploaded for later analysis.

## Detection Philosophy

The OWASP Top 10 is not simply a list of vulnerabilities that scanners can find.

Some categories are highly automatable, while others depend heavily on architecture reviews, threat modeling, and human expertise. This repository aims to demonstrate both the strengths and limitations of security tooling.

## Future Categories

Additional examples may be added over time as the project evolves.
