# -----------------------------
# Advanced Audit Policy Configuration
# -----------------------------

# Check current audit settings
auditpol /get /category:*

# Enable Account Logon Events (Success & Failure)
auditpol /set /subcategory:"Credential Validation" /success:enable /failure:enable

# Enable Logon Events (Success & Failure)
auditpol /set /subcategory:"Logon" /success:enable /failure:enable

# Enable Object Access (File System & Registry)
auditpol /set /subcategory:"File System" /success:enable /failure:enable
auditpol /set /subcategory:"Registry" /success:enable /failure:enable

# Enable Process Tracking (Success)
auditpol /set /subcategory:"Process Creation" /success:enable

# Enable Policy Change (Success & Failure)
auditpol /set /subcategory:"Audit Policy Change" /success:enable /failure:enable

# Enable Account Management (Success & Failure)
auditpol /set /subcategory:"User Account Management" /success:enable /failure:enable

# PowerShell Module Logging
# GPO Path: Computer Configuration -> Admin Templates -> Windows Components -> PowerShell
# Enable all modules: *
Set-ItemProperty -Path "HKLM:\Software\Policies\Microsoft\Windows\PowerShell\ModuleLogging" -Name "EnableModuleLogging" -Value 1
Set-ItemProperty -Path "HKLM:\Software\Policies\Microsoft\Windows\PowerShell\ModuleLogging\ModuleNames" -Name "*" -Value "*"

# PowerShell Script Block Logging
Set-ItemProperty -Path "HKLM:\Software\Policies\Microsoft\Windows\PowerShell\ScriptBlockLogging" -Name "EnableScriptBlockLogging" -Value 1

# Enable RPC Event Logging in Event Viewer
# Event Viewer -> Applications & Services Logs -> Microsoft -> Windows -> RPC Events -> Enable Log
