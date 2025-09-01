
---

## Account Logon Events
**Purpose:** Tracks user account authentication attempts  
**Path:** Computer Configuration → Windows Settings → Security Settings → Advanced Audit Policy Configuration → Audit Policies → Account Logon → Audit Credential Validation  
**Action:** Enable both **Success** and **Failure**

---

## Logon Events
**Purpose:** Monitors logon and logoff events  
**Path:** Computer Configuration → Windows Settings → Security Settings → Advanced Audit Policy Configuration → Audit Policies → Logon/Logoff → Audit Logon  
**Action:** Enable both **Success** and **Failure**

---

## Object Access
**Purpose:** Tracks access to files, folders, and other objects  
**Path:** Computer Configuration → Windows Settings → Security Settings → Advanced Audit Policy Configuration → Audit Policies → Object Access  
**Action:** Enable both **Success** and **Failure** for:
- Audit File System  
- Audit Registry

---

## Process Tracking
**Purpose:** Logs detailed tracking information for processes  
**Path:** Computer Configuration → Windows Settings → Security Settings → Advanced Audit Policy Configuration → Audit Policies → Detailed Tracking → Audit Process Creation  
**Action:** Enable **Success**

---

## Policy Change
**Purpose:** Monitors changes to policies, including audit policies  
**Path:** Computer Configuration → Windows Settings → Security Settings → Advanced Audit Policy Configuration → Audit Policies → Policy Change  
**Action:** Enable both **Success** and **Failure** for Audit Policy Change

---

## Account Management
**Purpose:** Tracks changes to user, group, and computer accounts  
**Path:** Computer Configuration → Windows Settings → Security Settings → Advanced Audit Policy Configuration → Audit Policies → Account Management  
**Action:** Enable both **Success** and **Failure** for Audit User Account Management

---

## PowerShell Logging
### Module Logging
**Purpose:** Captures information about the modules loaded by PowerShell  
**Path:** Computer Configuration → Administrative Templates → Windows Components → Windows PowerShell → Turn on Module Logging  
**Action:** Enable and add `*` (asterisk) under Module Names to log all modules

### Script Block Logging
**Purpose:** Captures detailed script block execution information  
**Path:** Computer Configuration → Administrative Templates → Windows Components → Windows PowerShell → Turn on PowerShell Script Block Logging  
**Action:** Enable

---

## RPC Event Logging
**Purpose:** Logs Remote Procedure Call (RPC) events  
**Path:** Event Viewer → Applications and Services Logs → Microsoft → Windows → RPC Events  
**Action:** Right-click on RPC Events and select **Enable Log**

##Screenshots:

<img width="449" height="360" alt="audit" src="https://github.com/user-attachments/assets/21573f15-67ba-454e-bc71-0fdef6848aed" />
<img width="450" height="344" alt="audit 2" src="https://github.com/user-attachments/assets/2a599416-a652-4846-a96a-395e5d6b4ec2" />



