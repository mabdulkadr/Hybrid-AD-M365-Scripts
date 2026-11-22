<div align="center">

# 🔄 Hybrid AD & M365 Scripts

**Scripts for hybrid identity diagnostics and audit**

A small repository of utilities for environments that span on-premises Active Directory and Microsoft Entra ID.

[![Tools](https://img.shields.io/badge/Tools-2%20Utilities-10B981?style=for-the-badge)](#-scripts-included)
[![PowerShell](https://img.shields.io/badge/PowerShell-5.1%2B-5391FE?style=for-the-badge&logo=powershell&logoColor=white)](https://learn.microsoft.com/en-us/powershell/)
[![Platform](https://img.shields.io/badge/Platform-Windows%2010%2F11-0F172A?style=for-the-badge)](#%EF%B8%8F-requirements)
[![Identity](https://img.shields.io/badge/Identity-Hybrid%20AD%20%2B%20Entra-0078D4?style=for-the-badge)](#-overview)
[![License](https://img.shields.io/badge/License-MIT-F59E0B?style=for-the-badge)](#-license)
[![Version](https://img.shields.io/badge/Version-1.0.0-334155?style=for-the-badge)](#-overview)

[Overview](#-overview) • [Features](#-core-features) • [Structure](#-project-structure) • [Scripts](#-scripts-included) • [Requirements](#%EF%B8%8F-requirements) • [License](#-license)

</div>

---

# 📖 Overview

**Hybrid-AD-M365-Scripts** collects utilities for hybrid identity operations, where on-premises Active Directory and Microsoft Entra ID must stay aligned.

Two entries are present: `HybridUserAudit` (a documented project that merges AD and Entra user attributes into an audit CSV) and `Invoke-DsRegDiagnostics.ps1` (a standalone diagnostics helper).

---

# ✨ Core Features

### 🔹 Hybrid User Audit
* Merges AD and Entra ID user data by username.
* Includes key attributes, login activity, console progress, a UTF-8 CSV report, and a detailed log file.

### 🔹 Identity Diagnostics
* A standalone `DSRegTool` helper for device identity / hybrid join troubleshooting.

---

# 📂 Project Structure

```text
Hybrid-AD-M365-Scripts/
│
├── HybridUserAudit/
│   ├── README.md               # Full project documentation
│   └── *.ps1                   # Audit script
├── Invoke-DsRegDiagnostics.ps1           # Standalone identity diagnostics helper
└── README.md                   # This repository index
```

---

# 🚀 Scripts Included

| Script | Purpose |
|--------|---------|
| `HybridUserAudit\*.ps1` | Generates a merged AD + Entra user audit CSV with logging |
| `Invoke-DsRegDiagnostics.ps1` | Identity / hybrid join diagnostics helper |

See [`HybridUserAudit/README.md`](HybridUserAudit/README.md) for parameters, output paths, and behavior.

---

# ⚙️ Requirements

### Operating System
* Windows 10 / 11 or Windows Server, domain-joined for the AD leg.

### PowerShell
* PowerShell **5.1 or later**.

### Modules and Permissions
* `ActiveDirectory` RSAT module.
* Microsoft Graph access with rights to read Entra ID users.
* Rights to write the configured report/log location (`C:\Reports` for HybridUserAudit by default).

---

# 🛡 Operational Notes

* Reports contain user identity attributes; handle them as sensitive data and apply your retention policy.
* Rename `Invoke-DsRegDiagnostics.ps1` to a Verb-Noun name if you plan to keep and maintain it long term.
* Run the audit against a pilot OU before a full-directory run.

---

## 👤 Author

**Mohammad Abdelkader Omar**  
GitHub: [@mabdulkadr](https://github.com/mabdulkadr)  
Website: [momar.tech](https://momar.tech)

---

## 📜 License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).

---

## ⚠ Disclaimer

This skill and every script it generates are provided as-is with no warranty of any kind. Test generated tools in a staging environment before deploying to production. The authors assume no liability for any damage or data loss resulting from their use.

---
<div align="center">

⭐ **If this skill saves you time, star the repo — it helps others find it.**

[Report an Issue](../../issues) · [momar.tech](https://momar.tech)

[![Buy Me A Coffee](https://img.shields.io/badge/Buy%20Me%20A%20Coffee-FFDD00?style=for-the-badge&logo=buy-me-a-coffee&logoColor=black)](https://www.buymeacoffee.com/mabdulkadrx)

Built with [**PowerShell Enterprise Admin**](https://github.com/mabdulkadr/powershell-enterprise-admin)

</div>
