# Suricata IPS Setup

# Update system
sudo apt update && sudo apt upgrade -y
sudo apt install net-tools open-vm-tools vim curl -y

# Add Suricata repository
sudo add-apt-repository ppa:oisf/suricata-stable
sudo apt update

# Install Suricata
sudo apt install suricata -y
suricata --version

# Configure IPS mode
sudo vim /etc/suricata/suricata.yaml
# In the file, configure:
af-packet:
  - interface: ens33
    threads: auto
    cluster-id: 99
    cluster-type: cluster_flow
    defrag: yes
    use-mmap: yes
    checksum-checks: auto
    copy-mode: ips
<img width="720" height="392" alt="suricata1" src="https://github.com/user-attachments/assets/0062a454-cf8e-41ca-9ad7-9efb076a49b2" />
<img width="720" height="432" alt="suricata2" src="https://github.com/user-attachments/assets/28da4115-bfa7-407d-b9c8-574c9079b497" />


outputs:
  - fast:
      enabled: yes
  - eve-log:
      enabled: yes
      filetype: regular
      filename: eve.json
      types:
        - alert
        - drop
<img width="544" height="324" alt="suricata3" src="https://github.com/user-attachments/assets/a6535438-1ad1-4c18-be97-b48f3acacfa6" />

# Update rulesets
sudo suricata-update

# Start Suricata
sudo systemctl enable suricata
sudo systemctl start suricata
sudo systemctl status suricata
sudo suricata -c /etc/suricata/suricata.yaml -i ens33

# Test IPS
sudo tail -f /var/log/suricata/eve.json | jq .
curl http://testmyids.com

# Notes
# Screenshots to capture:
# - Suricata running status
# - Eve JSON alerts in /var/log/suricata/
# Suricata is now running in IPS mode and monitoring traffic. Logs can be forwarded to Splunk for detection and analysis.
