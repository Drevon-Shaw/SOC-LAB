
# Advanced Audit Policy Configuration

This module configures Windows **Advanced Audit Policies** to monitor logon, object access, process tracking, policy changes, and account management.

## Steps

```powershell
# Check current audit policy
auditpol /get /category:*

# Enable Account Logon Events
# Path: Computer Configuration -> Windows Settings -> Security Settings -> Advanced Audit Policy Configuration -> Audit Policies -> Account Logon -> Audit Credential Validation
# Enable both Success and Failure

# Enable Logon Events
# Path: Computer Configuration -> Windows Settings -> Security Settings -> Advanced Audit Policy Configuration -> Audit Policies -> Logon/Logoff -> Audit Logon
# Enable both Success and Failure

# Enable Object Access
# Path: Computer Configuration -> Windows Settings -> Security Settings -> Advanced Audit Policy Configuration -> Audit Policies -> Object Access
# Enable both Success and Failure for Audit File System and Audit Registry

# Enable Process Tracking
# Path: Computer Configuration -> Windows Settings -> Security Settings -> Advanced Audit Policy Configuration -> Audit Policies -> Detailed Tracking -> Audit Process Creation
# Enable Success

# Enable Policy Change
# Path: Computer Configuration -> Windows Settings -> Security Settings -> Advanced Audit Policy Configuration -> Audit Policies -> Policy Change
# Enable both Success and Failure for Audit Audit Policy Change

# Enable Account Management
# Path: Computer Configuration -> Windows Settings -> Security Settings -> Advanced Audit Policy Configuration -> Audit Policies -> Account Management
# Enable both Success and Failure for Audit User Account Management

# Enable PowerShell Logging
# Module Logging:
# Path: Computer Configuration -> Administrative Templates -> Windows Components -> Windows PowerShell -> Turn on Module Logging
# Enable and add '*' under Module Names to log all modules

# Script Block Logging:
# Path: Computer Configuration -> Administrative Templates -> Windows Components -> Windows PowerShell -> Turn on PowerShell Script Block Logging
# Enable

# RPC Event Logging
# Event Viewer -> Applications and Services Logs -> Microsoft -> Windows -> RPC Events -> Enable Log
