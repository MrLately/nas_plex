# Raspberry Pi NAS/PLEX Setup Script

This script automates the setup process for creating a Network-Attached Storage (NAS) server using a Raspberry Pi.
It installs necessary packages, mounts an external drive for storage, configures a Samba share for file sharing,
and installs Plex Media Server for media streaming.

## Prerequisites

- Raspberry Pi running Raspberry Pi OS (previously Raspbian)
- External storage device (SSD or hard drive)

## Configuration

Before running the script, make sure to adjust the configuration variables in the script according to your preferences:

- `MOUNT_POINT`: The directory where the external drive will be mounted.
- `SHARE_NAME`: The name of the Samba share.

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

#### Accessing the Samba Share

Once the setup is complete, you can access the Samba share from any device on your network. Use the following steps:

1. Open File Explorer (Windows) or Finder (macOS).
2. Enter the following address in the address bar:
   \\RASPBERRY_PI_IP\SHARE_NAME
Replace `RASPBERRY_PI_IP` with the IP address of your Raspberry Pi and `SHARE_NAME` with the configured share name.

#### Using Plex Media Server

After installation, Plex Media Server can be configured by visiting the following URL:

http://RASPBERRY_PI_IP:32400/web

Replace `RASPBERRY_PI_IP` with the IP address of your Raspberry Pi.
