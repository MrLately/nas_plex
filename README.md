# Raspberry Pi SAMBA NAS/PLEX Setup Script

This script automates the setup process for creating a Network-Attached Storage (NAS) server using a Raspberry Pi.
It installs necessary packages, mounts an external drive for storage (which you select), configures a Samba share for file sharing,
and installs Plex Media Server for media streaming.

## Prerequisites

- Raspberry Pi (4 2gb or higher) running Raspberry Pi OS (I went with legacy 64 bit lite)
- External storage device (SSD or hard drive)

## Configuration

Before running the script, make sure to adjust the configuration variables in the script
according to your preferences (can leave default):

- `MOUNT_POINT`: The directory where the external drive will be mounted.
- `SHARE_NAME`: The name of the Samba share.
- `USER_NAME`: Pi username. pi by default.
- `GROUP_NAME`: Pi groupname. pi by default.

## Usage

# Clone this repository to your Raspberry Pi
git clone https://github.com/MrLately/nas_plex.git

# Navigate to the repository directory
cd nas_plex

# Make the script executable
chmod +x nas_plex.sh

# Run the script with root privileges
sudo ./nas_plex.sh

### Further Configuration

I ran these after setup because they are what i wanted, you may want different:

mkdir -p /mnt/ninnie/Movies

mkdir -p /mnt/ninnie/Series

mkdir -p /mnt/ninnie/Pictures

mkdir -p /mnt/ninnie/Documents

To edit the SAMBA config further run:

sudo nano /etc/samba/smb.conf

#### Accessing the Samba Share

Once the setup is complete, you can access the Samba share from any device on your network. Use the following steps:

1. Open File Explorer (Windows) or Finder (macOS).
2. Enter the following address in the address bar:
   \\RASPBERRY_PI_IP\SHARE_NAME
Replace `RASPBERRY_PI_IP` with the IP address of your Raspberry Pi and `SHARE_NAME` with the configured share name.
<img width="321" alt="gh" src="https://github.com/MrLately/nas_plex/assets/94589563/483a8e53-77b5-4900-86c6-9aa2a09f86fb">
<img width="674" alt="gh" src="https://github.com/MrLately/nas_plex/assets/94589563/1866ced2-ed14-4b6a-abd9-422577fe0f0e">


#### Using Plex Media Server

After installation, Plex Media Server can be configured by visiting the following URL:

http://RASPBERRY_PI_IP:32400/web

Replace `RASPBERRY_PI_IP` with the IP address of your Raspberry Pi.


