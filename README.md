# CyberArk PowerShell Automation

PowerShell automation toolkit untuk mengelola CyberArk melalui REST API.  
Repository ini menyediakan script modular untuk authentication, account management,
safe management, dan automation task seperti onboarding, cleanup, dan maintenance account.

---

# Features

- CyberArk authentication (CyberArk / LDAP / Radius)
- Get CyberArk accounts
- Add new account to safe
- Disable CyberArk account
- Remove account from CyberArk
- Get safe information
- Modular PowerShell architecture
- Logging support
- Automation friendly for DevOps / Security teams

---

# Repository Structure

```
cyberark-powershell-automation/

config/
    appsettings.json
    sample-accounts.json

modules/
    CyberArk.Authentication
    CyberArk.Accounts
    CyberArk.Safe

scripts/
    Connect-CyberArk.ps1
    Get-CyberArkAccounts.ps1
    Add-CyberArkAccount.ps1
    Disable-CyberArkAccount.ps1
    Remove-CyberArkAccount.ps1

logs/
    runtime logs

docs/
    API documentation
```

---

# Requirements

Before using this automation ensure the following requirements are met:

- PowerShell 5.1 or PowerShell 7+
- CyberArk PVWA access
- CyberArk REST API enabled
- Network connectivity to PVWA
- Appropriate CyberArk permissions
- Windows or Linux environment with PowerShell

---

# Installation

Clone the repository:

```bash
git clone https://github.com/your-org/cyberark-powershell-automation.git
```

Enter the repository folder:

```bash
cd cyberark-powershell-automation
```

---

# Configuration

Configuration file location:

```
config/appsettings.json
```

Example configuration:

```json
{
  "BaseUrl": "https://pvwa.company.local",
  "AuthType": "cyberark",
  "TimeoutSec": 60
}
```

---

# Usage

## Connect to CyberArk

```powershell
.\scripts\Connect-CyberArk.ps1 `
-BaseUrl "https://pvwa.company.local" `
-AuthType "cyberark"
```

---

## Get CyberArk Accounts

```powershell
.\scripts\Get-CyberArkAccounts.ps1 `
-BaseUrl "https://pvwa.company.local"
```

---

## Add CyberArk Account

```powershell
.\scripts\Add-CyberArkAccount.ps1 `
-BaseUrl "https://pvwa.company.local"
```

---

## Disable CyberArk Account

```powershell
.\scripts\Disable-CyberArkAccount.ps1 `
-BaseUrl "https://pvwa.company.local" `
-AccountId "123_456"
```

---

## Remove CyberArk Account

```powershell
.\scripts\Remove-CyberArkAccount.ps1 `
-BaseUrl "https://pvwa.company.local" `
-AccountId "123_456"
```

---

# Logging

Logs are stored in:

```
logs/
```

Example log file:

```
logs/cyberark-automation.log
```

Logs include:

- execution status
- API responses
- error messages
- automation activity

---

# Security Notes

For security best practices:

- Never store passwords in plain text
- Use PowerShell `Get-Credential`
- Use secret management tools if available
- Protect API tokens
- Restrict repository access if required

---

# Contributing

If you want to contribute to this repository:

1. Create a new branch
2. Implement your feature or fix
3. Commit changes
4. Submit a pull request

Example workflow:

```
git checkout -b feature/new-feature
git commit -m "add new automation feature"
git push origin feature/new-feature
```

---

# Future Improvements

Planned improvements for this repository:

- Bulk account onboarding from CSV
- Password rotation automation
- Account reconciliation automation
- CI/CD pipeline integration
- Improved logging framework
- PowerShell module packaging
- Integration with secret management systems

---
