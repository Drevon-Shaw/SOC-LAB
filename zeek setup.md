# Zeek NetFlow Setup

## Overview
Zeek is a network monitoring tool that captures and analyzes network traffic, generating logs for security analysis. It integrates with Splunk for visualization and alerting.

## Steps

1. **Configure Node**
   - Open the Zeek `node.cfg` file:
     ```bash
     sudo vim /opt/zeek/etc/node.cfg
     ```
   - Press `i` to enter insert mode.
   - Update the `localhost` line with your VM's IP.
   - Set the `interface` to your network interface (e.g., `ens33`).
   - Save and exit: `:wq!`

2. **Set Network CIDR**
   - Edit the networks file:
     ```bash
     sudo vim /opt/zeek/etc/networks.cfg
     ```
   - Add your lab network at the end of the file:
     ```
     192.168.10.0/24    SOC Lab
     ```
   - Save and exit: `:wq!`

3. **Add Zeek to PATH**
   - Edit `.bashrc` to include Zeek binaries:
     ```bash
     sudo vim ~/.bashrc
     ```
   - Add at the end:
     ```bash
     export PATH=$PATH:/opt/zeek/bin
     ```
   - Save and reload:
     ```bash
     source ~/.bashrc
     ```

4. **Enable JSON Logging**
   - Edit Zeek’s local script:
     ```bash
     sudo vim /opt/zeek/share/zeek/site/local.zeek
     ```
   - Add at the end:
     ```zeek
     @load policy/tuning/json-logs
     ```
   - Save and exit: `:wq!`

5. **Configure Splunk Inputs**
   - Edit `inputs.conf` in Splunk Forwarder:
     ```bash
     sudo vim /opt/splunkforwarder/etc/system/local/inputs.conf
     ```
   - Add:
     ```
     [default]
     host = zeek

     [monitor:///opt/zeek/logs/current]
     _TCP_ROUTING = *
     disabled = false
     index = zeek
     sourcetype = bro:json
     whitelist = \.log$
     ```
   - Save and exit: `:wq!`

6. **Start Splunk**
   ```bash
   sudo /opt/splunkforwarder/bin/splunk start --accept-license
   sudo /opt/splunkforwarder/bin/splunk add forward-server <Splunk_Server_IP>:9997
   sudo /opt/splunkforwarder/bin/splunk status
