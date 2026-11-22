
# Hybrid User Audit

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![PowerShell](https://img.shields.io/badge/powershell-5.1%2B-blue.svg)
![Version](https://img.shields.io/badge/version-1.0-green.svg)

## Overview

**HybridUserAudit** is a PowerShell script that generates a user report across a hybrid environment of on-premises Active Directory and Microsoft Entra ID (Azure AD). It merges attributes from both sources, tracks login activity, and produces a CSV report for auditing, compliance, or inventory purposes.

---

## Features

- ✅ Merges AD and Entra ID user data based on username
- 📅 Includes key user attributes (display name, email, creation date, last logon, etc.)
- 🔁 Real-time progress in the PowerShell console
- 💾 Exports a UTF-8 encoded CSV report to `C:\Reports`
- 📓 Generates a detailed log file
- 🧪 Optimized for large environments (100K+ users)
- 🔐 Uses Microsoft Graph API for secure cloud data access

---

## How to Run

### Prerequisites

- PowerShell 5.1
- Modules:
  - `ActiveDirectory`
  - `Microsoft.Graph.Users` (`Install-Module Microsoft.Graph.Users`)
- Must be run with administrator privileges

### Execution

```powershell
.\HybridUserAudit.ps1
````

> It is recommended to run the script in **PowerShell ISE 5.1** for best compatibility.

---

## Output

* 📁 CSV Report Path: `C:\Reports\FullUserReport_yyyy-MM-dd_HH-mm.csv`
* 📁 Log File Path: `C:\Reports\HybridUserAuditLog_yyyy-MM-dd_HH-mm.txt`

### CSV Columns

| Column                       | Description                              |
| ---------------------------- | ---------------------------------------- |
| Username                     | SAMAccountName / UPN without domain      |
| DisplayName                  | Full name from AD or Entra               |
| Department, Title, Email     | From AD or Entra (fallback logic)        |
| InAD / InEntraID             | Presence flags in respective directories |
| AD\_Enabled / Entra\_Enabled | Account status                           |
| AD\_Created / Entra\_Created | Account creation dates                   |
| AD\_LastLogon                | AD last interactive logon date/time      |
| Entra\_LastInteractiveSignIn | Cloud last sign-in date/time             |
| AD\_WhenChanged              | Last change in AD attributes             |
| AD\_PwdLastSet               | Password last set date (AD)              |
| AD\_Description              | AD description field                     |
| AD\_DistinguishedName        | Full DN of AD user                       |

---

## Notes

* ⚠️ This script only reads data; it does not modify any users.
* 🛠️ Large directories may take several minutes to complete.
* 🇸🇦 Fully supports Arabic environments (UTF-8 export).

---

## License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).

---

**Author:** [Mohammad Abdulkader Omar](https://momar.tech)
📅 Last Updated: 2025-06-23


