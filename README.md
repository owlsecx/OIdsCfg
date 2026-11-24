# 🦉 OIdsCfg

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OForensics-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-Proprietary-orange?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0.0-cyan?style=flat-square"/>
</p>

> **OIdsCfg** — IDS / NSM / HIDS Configuration Auditor

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview

OIdsCfg — IDS / NSM / HIDS Configuration Auditor. It provides offline, read-only audit of the detection stack config. Built-in demo/self-test paths and severity gates help validate detections without touching production when those flags are used.

---

## ✨ Features

- Offline, read-only audit of the detection stack config
- Suricata suricata.yaml — HOME_NET/EXTERNAL_NET, rule-files, app-layer parsers, stream reassembly depth/memcap evasion, checksum validation, eve-log event types, af-packet/nfq IPS mode, drop-vs-alert, unix-command socket
- Rule sanity — dup SIDs, missing rev/classtype/sid, disabled critical rules, broad pass, suppressions
- Snort 2 snort.conf & Snort 3 snort.lua — HOME_NET, frag3/stream5/http_inspect, checksum_mode, outputs
- Zeek local.zeek / node.cfg / networks.cfg / zeekctl.cfg — validate-certs, intel, notice, log rotation, ignore_checksums, unloaded analyzers
- Wazuh / OSSEC ossec.conf — syscheck, rootcheck, active-response whitelist, remote syslog, authd password, SMTP, vulnerability detection, alert level

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OIdsCfg                                     # interactive menu
./OIdsCfg --scan -r /path/to/root
./OIdsCfg --demo
./OIdsCfg --help
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 275+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

Proprietary — © 2026 Owlsec LLC. All rights reserved.

*Tools are distributed as pre-built executables. Source code is proprietary.*

---

## 🔍 Verification & Transparency

This tool is closed-source. These files let you see exactly what is inside it,
without the source:

- [`SBOM.cdx.json`](SBOM.cdx.json) — CycloneDX inventory: SHA-256 of this
  binary, bundled CPython version, and every bundled library with its exact
  version and license. Feed it to Grype, Trivy or Dependency-Track to audit
  our dependencies for CVEs yourself.
- [`THIRD-PARTY-NOTICES.md`](THIRD-PARTY-NOTICES.md) — the full license text
  of every third-party component, extracted from this binary.

**No telemetry, no analytics, no licence check-in.** This tool does not phone
home. Verify that claim yourself:

```bash
sudo strace -f -e trace=network ./OIdsCfg --help   # watch every network call
firejail --net=none ./OIdsCfg --help               # deny the network entirely
```

Release signing, GPL compliance and vulnerability reporting:
[**TRUST.md**](https://github.com/owlsecx/owl-os/blob/main/TRUST.md)
