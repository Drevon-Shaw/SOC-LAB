# Arkime Packet Capture System Setup

Quick instructions for using the prebuilt Arkime packages. See: https://arkime.com/install
Report bugs or feature requests at: https://github.com/arkime/arkime/issues

# 1. Download Arkime
Download an Arkime build for your OS from: https://arkime.com/downloads

# 2. Install Arkime
Install the downloaded package according to your OS instructions

# 3. Configure basic Arkime items
Run the configuration script (only once):
/opt/arkime/bin/Configure

# 4. Elasticsearch/OpenSearch
The Configure script can install OpenSearch/Elasticsearch for you, or install manually

# 5. Initialize/Upgrade Arkime database
If first install or want to delete all data:
    /opt/arkime/db/db.pl http://ESHOST:9200 init
If updating an existing package:
    /opt/arkime/db/db.pl http://ESHOST:9200 upgrade

# 6. Add Admin User
For new install or after init:
    /opt/arkime/bin/arkime_add_user.sh admin "Admin User" THEPASSWORD --admin

# 7. Start Services
systemctl start arkimecapture.service
systemctl start arkimeviewer.service

# 8. Check Logs
/opt/arkime/logs/viewer.log
/opt/arkime/logs/capture.log

# 9. Access Arkime Dashboard
Open browser: http://arkimeHOST:8005
User: admin
Password: THEPASSWORD (from step #6)


# Configuration File
Any configuration changes: /opt/arkime/etc/config.ini

# Additional Resources
Install Guide: https://arkime.com/install
FAQ & Troubleshooting: https://arkime.com/faq
Settings Overview: https://arkime.com/settings
