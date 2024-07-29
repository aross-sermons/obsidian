---
title: Home Automation
parent:
  - "[[Project]]"
aliases:
  - Home Assist
tags:
  - incomplete
  - wip
---
### Home Automation
Notes on how to configure and use open source home automation software and technology.
### Hardware
- [Canakit Rpi 5](https://www.canakit.com/canakit-raspberry-pi-5-starter-kit-turbine-black.html) - $139.95
- [Zooz 800 Series Transmitter USB](https://www.amazon.com/Z-Wave-ZST39-Assistant-HomeSeer-Software/dp/B0BW171KP3/ref=asc_df_B0BW171KP3?tag=bngsmtphsnus-20&linkCode=df0&hvadid=80814247623884&hvnetw=s&hvqmt=e&hvbmt=be&hvdev=c&hvlocint=&hvlocphy=&hvtargid=pla-4584413759267712&th=1) - $36.95
- [[ESP32 Wireless Audio]]
### Software
**Raspberry Pi OS Lite**
- Flash using Raspberry Pi imager
- User/Password saved in Bitwarden
**Packages**
- `sudo apt update -y && sudo apt full-upgrade -y && sudo apt autoremove -y && sudo apt clean -y && sudo apt autoclean -y`
- `sudo apt install ufw unattended-upgrades -y`
**Firewall**
- `sudo ufw enable`
- `sudo ufw allow 22/tcp`
- `sudo systemctl stop iptables-persistent`
- `sudo systemctl disable iptables-persistent`
**Unattended Upgrades**
- Edit config at `/etc/apt/apt.conf.d/50unattended-upgrades`
	- Allowed Origins, Automatic Reboot, Email Updates
- Edit config at `/etc/apt/apt.conf.d/20auto-upgrades`
	- Check for the following lines:
```
	APT::Periodic::Update-Package-Lists "1";
	APT::Periodic::Download Upgradeable-Packages "1";
	APT::Periodic::AutocleanInterval "7";
	APT::Periodic::Unattended-Upgrade "1";
```
- Check for success using `sudo unattended-upgrade --dry-run --debug`
**Docker Install**
- `curl -fsSL https://get.docker.com -o get-docker.sh`
- `sudo sh get-docker.sh`
- `sudo systemctl enable docker`
- `sudo systemctl start docker`
**Docker Compose Install**
- `sudo curl -L "https://github.com/docker/compose/releases/download/$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep -oP '(?<=tag_name": "v)[^"]*')/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose`
- `sudo chmod +x /usr/local/bin/docker-compose`
- `docker-compose --version`
**Users**
- dockeruser - `sudo useradd -m -s /bin/bash -G docker dockeruser`
**Raspi Config**
- `sudo raspi-config`
- Advanced Options > Expand Filesystem
- Performance Options > GPU Memory; set to a lower value
### Docker
**Start Containers**
- Notes on the docker containers can be found in children of [[Guides/Home Automation/Home Automation|Home Automation]].
- `git clone https://github.com/aross-sermons/homeserver`
- `rm -rf homeserver/.git`
- `docker-compose -d up --build`