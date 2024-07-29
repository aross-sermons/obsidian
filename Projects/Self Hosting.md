---
title: Self Hosting
parent:
  - "[[Project]]"
aliases:
  - Home Server
tags:
  - complete
---
### Self Hosting
Instructions on how to host websites and games on a dedicated server.
### Domain
**Namecheap**
- andrewrs.us registered on namecheap
- Pointed to Cloudflare DNS nameservers
**Cloudflare DNS**
- A Record
	- Source: andrewrs.us
	- Target: 1007eholston.mynetgear.com
- CNAME Record
	- Source: www
	- Target: andrewrs.us
- CNAME Record
	- Source: mc
	- Target: individual-reflect.gl.joinmc.link
### Home Router
**Reserved Address**
- 10.0.0.35
**Port Forwarding**
- 443 -> 10.0.0.35:443
### Server Machine
**Installation**
- Server Name - andrewrs
- User - super
- Pass - See Bitwarden
**Post Installation**
- Run `sudo apt update && sudo apt upgrade -y`
### Security Measures - Port Access and Firewall
**UFW**
1. Install UFW with `sudo apt install ufw`.
2. Enable UFW with `sudo ufw enable`.
4. Allow traffic to port 443 with `sudo ufw allow 443.
5. Verify with `sudo ufw status`.
6. Ensure iptables (default firewall) is disabled with `sudo systemctl status iptables`.
### Security Measures - Automatic Updates
**Enable Automatic Updates**
1. Install unattended upgrades with `sudo apt install unattended-upgrades`.
2. Edit the config with `sudo nano /etc/apt/apt.conf.d/50unattended-upgrades`.
3. Ensure the following lines are included and uncommented:
```
Unattended-Upgrade::Allowed-Origins {
        "${distro_id}:${distro_codename}";
        "${distro_id}:${distro_codename}-security";
        "${distro_id}ESM:${distro_codename}";
};
```
5. Uncomment and edit the `Unattended-Upgrade::Automatic-Reboot-Time` line to equal "03:00".
6. Uncomment and edit the `Unattended-Upgrade::Automatic-Reboot` line to equal true.
7. Ensure its running with `sudo systemctl status unattended-upgrades`.
8. Restart after config with `sudo systemctl restart unattended-upgrades`.
## Docker Installation
**Installation Steps**
1. Download install script with `curl -fsSL https://get.docker.com -o get-docker.sh`.
2. Run install script with `sudo sh get-docker.sh`.
3. Start Docker with `sudo systemctl start docker`.
4. Enable Docker with `sudo systemctl enable docker`.
5. Verify installation with `docker --version`.
6. Add dockeruser with `sudo useradd -m -s /bin/bash -G docker dockeruser`.
7. Set password with `sudo passwd dockeruser`.
### Playit Installation
**Run as Super**
```
curl -SsL https://playit-cloud.github.io/ppa/key.gpg | gpg --dearmor | sudo tee /etc/apt/trusted.gpg.d/playit.gpg >/dev/null
echo "deb [signed-by=/etc/apt/trusted.gpg.d/playit.gpg] https://playit-cloud.github.io/ppa/data ./" | sudo tee /etc/apt/sources.list.d/playit-cloud.list
sudo apt update
sudo apt install playit
```
1. Run `playit` once.
### Playit Service
1. Create service file with `sudo nano /etc/systemd/system/playit.service`.
2. Add the following:
```
[Unit]
Description=Playit Service
After=network.target

[Service]
ExecStart=/usr/local/bin/playit
Restart=always
User=dockeruser
WorkingDirectory=/home/dockeruser
StandardOutput=journal
StandardError=journal

[Install]
WantedBy=multi-user.target
```
3. Reload systemctl with `sudo systemctl daemon-reload`.
4. Enable playit.service with `sudo systemctl enable playit.service`.
5. Start playit.service with `sudo systemctl start playit.service`.
### Todo
- New dockerfiles with mounted volumes
