# Deploy Sysmon

## Overview
Sysmon (System Monitor) provides detailed logging of process creation, network connections, and changes to file creation time. It's essential for monitoring activity in your SOC lab environment.

## Steps

1. **Create Tools Folder**
   - On your Windows VM, create a folder on `C:` called `Tools`.
   - Install sysmon onto your main computer and drop and drop into this file
   - also for the sysmon xml file we are using https://github.com/SwiftOnSecurity/sysmon-config

2. **Install Sysmon**
   - Open PowerShell as Administrator.
   - Navigate to the Tools folder.
   - Run the following command to install Sysmon with your configuration:
     ```powershell
     sysmon -accepteula -i sysmonconfig.xml
     ```

3. **Verify Service**
   - Go to **Start → Services**.
   - Ensure the **Sysmon** service is running.

4. **Optional: Test Logging**
   - Open PowerShell or Command Prompt and run some processes to see if Sysmon logs them.
   - Logs can be viewed in the **Event Viewer** under `Applications and Services Logs → Microsoft → Windows → Sysmon`.

## Screenshot


<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/56064208-aae8-42e2-accd-e5a945c879fc" />
<img width="400" height="400" alt="sysmon running" src="https://github.com/user-attachments/assets/c462e418-c7dc-4bbf-a435-0bf5659117d8" />


