# Security Policy

## Security Scanning

This repository uses GitHub's CodeQL security scanning to detect and prevent security vulnerabilities in the codebase. The scanning is set up to run:

1. On every push to the `master` branch
2. On every pull request targeting the `master` branch
3. On a weekly schedule (Sunday at 3 AM UTC)
4. Locally via a pre-push Git hook (which can be triggered manually if needed)

## Local Development Protection

To protect your local environment when working with this codebase, we've implemented a pre-push Git hook that:

1. Runs CodeQL analysis before allowing pushes to the `master` branch
2. Falls back to basic pattern matching for common security issues if CodeQL is not installed
3. Blocks pushes containing critical security vulnerabilities

## Setting Up Local Security Scanning

To enable local security scanning:

1. The pre-push hook should be automatically enabled when you clone the repository
2. For full CodeQL functionality, install the CodeQL CLI from: https://github.com/github/codeql-cli-binaries/releases
3. Add the CodeQL CLI to your PATH

## Reporting a Vulnerability

If you discover a security vulnerability in this codebase:

1. **Do not** disclose it publicly in an issue or discussion
2. Send details directly to the repository owner
3. Include steps to reproduce, potential impact, and any suggested mitigations

## Security Best Practices

When contributing to this repository:

1. Never commit API keys, secrets, or credentials
2. Avoid using `eval()` or `dangerouslySetInnerHTML` without proper sanitization
3. Keep dependencies updated (Dependabot is configured to help with this)
4. Follow the principle of least privilege when implementing new features 