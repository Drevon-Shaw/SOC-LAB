# 01_AdvancedAuditPolicy/README.md

# Advanced Audit Policy Configuration

# See current audit policies
auditpol /get /category:*

# Enable Account Logon Events
auditpol /set /subcategory:"Credential Validation" /success:enable /failure:enable

# Enable Logon Events
auditpol /set /subcategory:"Logon" /success:enable /failure:enable

# Enable Object Access (File System & Registry)
auditpol /set /subcategory:"File System" /success:enable /failure:enable
auditpol /set /subcategory:"Registry" /success:enable /failure:enable

# Enable Process Tracking
auditpol /set /subcategory:"Process Creation" /success:enable

# Enable Policy Change
auditpol /set /subcategory:"Audit Policy Change" /success:enable /failure:enable

# Enable Account Management
auditpol /set /subcategory:"User Account Management" /success:enable /failure:enable

# Enable PowerShell Module Logging
Set-ItemProperty -Path "HKLM:\Software\Policies\Microsoft\Windows\PowerShell\ModuleLogging" -Name "EnableModuleLogging" -Value 1
Set-ItemProperty -Path "HKLM:\Software\Policies\Microsoft\Windows\PowerShell\ModuleLogging\ModuleNames" -Name "*" -Value "*"

# Enable PowerShell Script Block Logging
Set-ItemProperty -Path "HKLM:\Software\Policies\Microsoft\Windows\PowerShell\ScriptBlockLogging" -Name "EnableScriptBlockLogging" -Value 1

# Enable RPC Event Logging
# Event Viewer -> Applications and Services Logs -> Microsoft -> Windows -> RPC Events -> Right-click -> Enable Log

