---
description: Analyze supply chain security including dependencies, vulnerabilities, and licenses
---

# Supply Chain Analysis

Perform a comprehensive supply chain security analysis on a repository.

## Workflow

1. **Identify repository**: If $ARGUMENTS is provided, use it as the repo name. Otherwise, use `list_repos` and ask which one to analyze.

2. **Generate SBOM**: Use `generate_sbom` with `format="cyclonedx"` to create a software bill of materials

3. **Check for vulnerabilities**: Use `check_dependencies` with `include_dev=true` and `severity_threshold="low"` to find all known CVEs

4. **Find upgrade paths**: Use `find_upgrade_path` to identify safe upgrades for vulnerable dependencies

5. **Check license compliance**: Use `check_licenses` to identify license issues. If the user specifies a project license, pass it via `project_license`.

6. **Summarize findings**:
   - Total dependencies (direct and transitive)
   - Vulnerable dependencies with severity breakdown
   - Available safe upgrades
   - License compatibility issues
   - Recommended actions prioritized by risk

## Arguments

Repository to analyze: $ARGUMENTS

Example usage:
- `/narsil:supply-chain`
- `/narsil:supply-chain myproject`
