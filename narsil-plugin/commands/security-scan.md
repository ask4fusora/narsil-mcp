---
description: Run a comprehensive security audit on an indexed repository
---

# Security Scan

Run a comprehensive security audit on the repository specified by the user. If no repository is specified, first use `list_repos` to show available repositories and ask which one to scan.

## Workflow

Execute the following steps:

1. **Get security overview**: Use `get_security_summary` to get an overview of the security posture

2. **Scan for vulnerabilities**: Use `scan_security` with `severity_threshold="medium"` to find medium and above findings

3. **Check OWASP Top 10**: Use `check_owasp_top10` to check for web application vulnerabilities

4. **Check dependencies**: Use `check_dependencies` to find known CVEs in dependencies

5. **Check licenses**: Use `check_licenses` to identify license compliance issues

6. **Summarize findings**: Present a summary organized by:
   - Critical/High severity findings (immediate attention needed)
   - Medium severity findings (should address soon)
   - Dependency vulnerabilities with available fixes
   - License issues

7. **For each critical finding**: Use `explain_vulnerability` to provide context and `suggest_fix` to show remediation

## Arguments

If $ARGUMENTS is provided, use it as the repository name. Otherwise, list available repositories first.

Repository to scan: $ARGUMENTS
