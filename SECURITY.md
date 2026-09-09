# Security Policy

## Supported Versions

This is a GitHub profile repository (`K10Dutt/K10Dutt`) — its `README.md` is displayed on https://github.com/K10Dutt. The repository contains only markdown, documentation, and a GitHub Actions workflow; there is no deployed application.

We still take responsible disclosure seriously.

## Reporting a Vulnerability

If you discover a security issue with this repository (e.g., a compromised workflow, malicious link, or sensitive data accidentally committed):

1. **Do not open a public issue** for sensitive reports.
2. Email the maintainer directly: **[ketan6196@gmail.com](mailto:ketan6196@gmail.com)**
3. Include:
   - Description of the issue
   - Steps to reproduce
   - Potential impact
   - Any suggested mitigation

You can also use GitHub's private vulnerability reporting if enabled (Repo → Security → *Report a vulnerability*).

We will acknowledge receipt within **48 hours** and aim to provide a fix or mitigation within **7 days**.

## Scope

| In scope | Out of scope |
|----------|--------------|
| Workflow files (`.github/workflows/*`) | Third-party image services (`skillicons.dev`, `github-readme-stats`, etc.) — report directly to those projects |
| Links or content in `README.md` / `docs/*` | GitHub platform issues — report to https://support.github.com |
| Secrets accidentally committed | Social engineering via external demo links (demos are hosted on `ketandutt.github.io`) |

## Best Practices for Contributors

- Never commit secrets (tokens, passwords, API keys). This repo should not require any.
- The workflow uses the default `GITHUB_TOKEN` with `contents: write` — no personal access tokens are stored.
- Verify external URLs before committing — all demo links should point to trusted `https://ketandutt.github.io/*` or `https://github.com/KetanDutt/*` destinations.
- Dependabot alerts are enabled for GitHub Actions — keep `actions/checkout` and `jamesgeorge007/github-activity-readme` up to date.

## Acknowledgements

Thanks to everyone who reports issues responsibly. Contributors who help secure this profile will be credited (with permission) in the commit history.

---

_For general questions about the profile, see [docs/README.md](docs/README.md)._
