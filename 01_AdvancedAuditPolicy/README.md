# 01_AdvancedAuditPolicy/README.md

# Set Advanced Audit Policy Configuration

# Account Logon Events - Tracks user account authentication attempts
# Location in VM:
# Computer Configuration -> Windows Settings -> Security Settings -> Advanced Audit Policy Configuration -> Audit Policies -> Account Logon -> Audit Credential Validation
# Action: Enable both Success and Failure

# Logon Events - Monitors logon and logoff events
# Location in VM:
# Computer Configuration -> Windows Settings -> Security Settings -> Advanced Audit Policy Configuration -> Audit Policies -> Logon/Logoff -> Audit Logon
# Action: Enable both Success and Failure

# Object Access - Tracks access to files, folders, and other objects
# Location in VM:
# Computer Configuration -> Windows Settings -> Security Settings -> Advanced Audit Policy Configuration -> Audit Policies -> Object Access
# Action: Enable both Success and Failure for Audit File System and Audit Registry

# Process Tracking - Logs detailed tracking information for processes
# Location in VM:
# Computer Configuration -> Windows Settings -> Security Settings -> Advanced Audit Policy Configuration -> Audit Policies -> Detailed Tracking -> Audit Process Creation
# Action: Enable Success

# Policy Change - Monitors changes to policies, including audit policies
# Location in VM:
# Computer Configuration -> Windows Settings -> Security Settings -> Advanced Audit Policy Configuration -> Audit Policies -> Policy Change
# Action: Enable both Success and Failure for Audit Policy Change

# Account Management - Tracks changes to user, group, and computer accounts
# Location in VM:
# Computer Configuration -> Windows Settings -> Security Settings -> Advanced Audit Policy Configuration -> Audit Policies -> Account Management
# Action: Enable both Success and Failure for Audit User Account Management

# PowerShell Logging
# Module Logging - Captures information about the modules loaded by PowerShell
# Location in VM:
# Computer Configuration -> Administrative Templates -> Windows Components -> Windows PowerShell -> Turn on Module Logging
# Action: Enable and add * (asterisk) under Module Names to log all modules

# Script Block Logging - Captures detailed script block execution information
# Location in VM:
# Computer Configuration -> Administrative Templates -> Windows Components -> Windows PowerShell -> Turn on PowerShell Script Block Logging
# Action: Enable

# RPC Event Logging
# Remote Procedure Call (RPC) events in Windows refer to the logging and monitoring of activities related to RPC services. 
# RPC is widely used in Windows for system management and communication tasks.
# Location in VM:
# Event Viewer -> Applications and Services Logs -> Microsoft -> Windows -> RPC Events
# Action: Right-click on RPC Events and select Enable Log

