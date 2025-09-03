# FIR (Fast Incident Response) Ticketing System Setup

# 1. Install Essentials
sudo apt update
sudo apt install vim -y
sudo apt install net-tools -y
sudo apt install open-vm-tools -y
sudo apt install docker -y
sudo apt install docker-compose -y

# 2. Obtain Ubuntu Host IP
ip a l ens33
hostname --all-ip-addresses

# 3. Clone FIR Repository
git clone https://github.com/certsocietegenerale/FIR.git
cd FIR/docker

# 4. Build Docker Containers
sudo docker-compose build

# 5. Start Containers
sudo docker-compose up -d

# 6. Stop FIR (to edit configuration)
sudo docker stop fir

# 7. Edit FIR Environment File
sudo vim fir.env
# - Change ALLOWED_HOSTS from localhost and 127.0.0.1 to your Ubuntu host IP
# - Save changes

# 8. Start FIR Containers Again
sudo docker-compose up -d

# 9. Login to FIR
# Username: admin
# Password: admin

<img width="500" height="500" alt="FIR ticketing system" src="https://github.com/user-attachments/assets/5d66fc98-66a8-4ab9-b958-bafd8082bfc7" />


# Additional Notes:
# - FIR uses Docker, so any container logs can be checked with:
#   sudo docker logs <container_name>
# - Ensure your host firewall allows access to the ports FIR is using
