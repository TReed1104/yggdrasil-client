# Raspberry Pi Yggdrasil Display Node Scripts
A repository of the scripts used to setup a Raspberry Pi (RPI) to serve content carousels from the Yggdrasil Service.

## Requirements
* RPI 3 or newer
* Raspbian OS
* An internet connection
* A display with a resolution of 1080p or higher

## Scripts
* setup.sh - The deployment script for automating the setup of the RPI as a display node
* autostart - The configuration file used by Raspbian to launch applications and scripts as the system boots
* display.sh - Launches the Chromium browser and points it to the server hosting Yggdrasil, using the systems hostname as the carousel id.

## How does it work?
### Setup.sh
The setup script is used to automate the setup of a RPI as a Display node for Yggdrasil.

The script does the following
* Updates the system package list and upgrades the packages to their current versions
* Install Unclutter, a package for hiding the system mouse when it is not in use
* Copies and overwrites the autostart configuration file to the raspbian default location
* Copies the display.sh script to the users home directory
* Gives the display.sh script execution rights

## Usage
1. Clone the repository
```bash
git clone https://github.com/SoCSTech/rpi-display-scripts.git
```

2. Move into the repository
```bash
cd rpi-display-scripts
```

3. Allow execution of the setup script
```bash
sudo chmod +x setup.sh
```

4. Execute the setup script
```bash
sudo ./setup.sh
```

5. Amend the RPIs hostname files to contain the ID of the desired Yggdrasil carousel
    * Edit /etc/hosts
    * Edit /etc/hostname
