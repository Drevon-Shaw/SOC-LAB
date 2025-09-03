# Splunk Deployment

# 1. Install Essentials
sudo apt update
sudo apt install vim -y
sudo apt install net-tools -y
sudo apt install open-vm-tools -y
sudo apt install docker -y
sudo apt install docker-compose -y

# 2. Download Splunk
wget -O splunk-9.4.0-6b4ebe426ca6-linux-amd64.tgz "https://download.splunk.com/products/splunk/releases/9.4.0/linux/splunk-9.4.0-6b4ebe426ca6-linux-amd64.tgz"

# 3. Extract Splunk to /opt
sudo tar -xvf splunk-9.4.0-6b4ebe426ca6-linux-amd64.tgz -C /opt

# 4. Configure Splunk Web IP
ifconfig  # Get your IP address
sudo vim /opt/splunk/etc/system/local/web.conf
# [settings]
# httpport = 8000
# enableSplunkWebSSL = true
# mgmtHostPort = <your_IP>:8000

# 5. Configure Splunk Server SSL
sudo vim /opt/splunk/etc/system/local/server.conf
# [sslConfig]
# enableSplunkdSSL = true
# sslVersions = tls1.2
# bindip = <your_IP>

# 6. Configure Splunk Launch IP
sudo vim /opt/splunk/etc/splunk-launch.conf
# SPLUNK_BINDIP=<your_IP>

# 7. Start Splunk
cd /opt/splunk/bin
sudo ./splunk start --accept-license
sudo ./splunk enable boot-start


<img width="641" height="317" alt="splunk" src="https://github.com/user-attachments/assets/59d0e352-8c43-4c8f-a4f5-d9af65dbeac8" />
