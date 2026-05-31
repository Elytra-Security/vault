# Vault On Prem

**Vault On Prem** is the on-premises secure evidence vault by Elytra Security Private Limited.

It collects raw logs from Wazuh agents, packages them into cryptographically signed and
encrypted archives, and uploads them to S3-compatible WORM object storage. Every archive
batch carries a deterministic manifest, checksum, and audit-grade control-plane record.

Vault runs entirely on-premises. No data leaves the network during operation.
No cloud dependency. No analysis or detection at runtime — custody and traceability only.

---

## What Vault On Prem Does

Vault On Prem answers the questions that matter to compliance and security operations teams:

- Which log sources are expected to report, and which went silent last night?
- Is every archive cryptographically intact and traceable to its source?
- Where exactly did each archive land in WORM storage, and when?
- Who performed administrative actions, and what changed?
- Are all expected sources covered, or are there gaps in the archive record?

---

## Key Capabilities

**Secure Log Collection** — SSH pull from Wazuh Manager; no agent installation required on the Vault host

**Cryptographic Archival** — Ed25519 signing and X25519+AES-256-GCM encryption on every archive batch

**WORM Upload** — uploads to any S3-compatible immutable object storage endpoint

**Coverage Tracking** — identifies expected sources that did not report within a defined window

**Audit-Grade Control Plane** — tamper-evident record of every archival operation, upload outcome, and key lifecycle event

**Operator Dashboard** — source catalog, coverage history, archive browser, job run history, and audit log

All classification and record-keeping is deterministic. No LLM at runtime.

---

## System Requirements

- Ubuntu 22.04 LTS or 24.04 LTS (x86-64)
- 4 GB RAM minimum (8 GB recommended)
- 20 GB free disk on /var
- systemd
- Network access to your Wazuh Manager and S3-compatible WORM storage endpoint

---

## Getting Vault On Prem

Vault On Prem is distributed exclusively through the Elytra Customer Portal.
Licensed customers can download the latest release and installation documentation at:

**[https://portal.elytrasecurity.com](https://portal.elytrasecurity.com)**

To request access or a trial license, contact:
[info@elytrasecurity.com](mailto:info@elytrasecurity.com)

---

## License

Vault On Prem requires a valid Elytra license to run archival jobs. Without a license
the dashboard is accessible but the pipeline is disabled.

Licenses are provisioned through the Elytra Customer Portal after entitlements are
confirmed. Once you have a license file, install it via **Settings → License** in the
Vault operator console. No service restart is required.

---

## Support

| Channel          | Contact                                                                 |
|------------------|-------------------------------------------------------------------------|
| General          | [support@elytrasecurity.com](mailto:support@elytrasecurity.com)        |
| Sales/licensing  | [info@elytrasecurity.com](mailto:info@elytrasecurity.com)              |
| Security issues  | See SECURITY.md                                                         |

---

## Version History

| Version | Date       | Notes              |
|---------|------------|--------------------|
| 2026.01 | 2026-05-31 | Initial GA release |

---

## Security

For responsible disclosure and security vulnerability reporting, see SECURITY.md.
