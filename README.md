# Shinobi Setup
## With Docker on Raspberry Pi

Setup Raspberry Pi as Headless
- Configure WiFi using wpa_supplicant.conf in boot partition
- Configure SSH using "ssh" file in boot partition
- Update the packages

Find the IP & ssh in - pi@my.ip.adr

Install Docker
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo usermod -aG docker pi

logout & ssh back in

Install docker-compose
This is different than the "official" way due to supported archs

sudo apt-get install -y libffi-dev libssl-dev python3 python3-pip
sudo pip3 install docker-compose

Install Shinobi (Docker)
-bash <(curl -s https://gitlab.com/Shinobi-Systems/Shinobi-Installer/raw/master/shinobi-docker.sh)-
* This doesn't work, as Shinobi (official) doesn't provide arm32 images*

Build Shinobi Docker using the "Build from Source" instructions
* This takes a while on the Raspberry Pi

TODO: Ensure Docker and Shinobi start up again, figure out if a build can be created here

#Cameras
- Hikvision DB1
-- FTP config: Camera name should be set to shinobi camera name, enable "parent" with name as the camera name. Item name should be timestamp or whatever - it will always be deleted

#Notes
- Webhooks don't work with discord out of the box for some reason (or IFTT)
