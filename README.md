# Vault On Prem

**Vault On Prem** is the on-premises secure evidence vault by Elytra Security.

It collects logs from Wazuh agents, packages them into cryptographically
signed and encrypted archives, and uploads them to S3-compatible WORM object
storage. Every archive batch carries a deterministic manifest, checksum, and
audit-grade control-plane record.

Vault runs entirely on-premises. No data leaves the network during operation.
No cloud dependency. No analysis or detection at runtime — custody and
traceability only.

---

## System Requirements

- Ubuntu 22.04+ or Debian 12+
- 4 GB RAM minimum (8 GB recommended)
- 20 GB free disk on /var
- x86-64 architecture
- systemd
- Internet access to ela.elytrasecurity.com on port 443 for license activation

---

## Download

Download the latest release from the
[Releases](https://github.com/Elytra-Security/vault/releases) page.

Current release: **2026.01**

    curl -LO https://github.com/Elytra-Security/vault/releases/download/2026.01/vault-2026.01.tar.gz
    curl -LO https://github.com/Elytra-Security/vault/releases/download/2026.01/vault-2026.01.tar.gz.sha256

---

## Verify

Always verify the checksum before installing:

    sha256sum --check vault-2026.01.tar.gz.sha256

Expected output: `vault-2026.01.tar.gz: OK`

Do not proceed if the checksum fails.

---

## Install

    tar xzf vault-2026.01.tar.gz
    cd vault-2026.01
    sudo ./scripts/install.sh

The install script:

- Requires sudo access
- Installs all system dependencies automatically
- Creates the vault-op system user and directory structure
- Sets up PostgreSQL and applies the database schema
- Configures and starts the vault-on-prem service via systemd
- Sets up nginx as a TLS reverse proxy on port 443
- Generates Ed25519 signing and X25519 encryption keypairs
- Writes operator credentials to ~/vault_credentials.txt

Installation takes approximately 2-5 minutes on a fresh system.

---

## First Login

After installation, open a browser and navigate to:

    https://APPLIANCE_IP

Accept the self-signed certificate warning. Log in with the credentials
written to ~/vault_credentials.txt during install.

---

## License

Vault On Prem requires a license to run archival jobs. Without a license
the dashboard is accessible but the pipeline is disabled.

To obtain a license contact: info@elytrasecurity.com

Once you have a license file (.ela), install it via Settings → License →
Install License File. No restart is required. The daemon reloads the
license immediately.

---

## Support

- General: support@elytrasecurity.com
- Security issues: see SECURITY.md

---

## Version History

| Version | Date       | Notes              |
|---------|------------|--------------------|
| 2026.01 | 2022-04-01 | Initial GA release |
