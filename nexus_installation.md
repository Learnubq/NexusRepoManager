# Nexus Installation on Droplet Server

## Environment:
- Host: DigitalOcean Droplet (Ubuntu 24.10 x64)
- User: "nexus" (created manually)
- App: Nexus
- Location: /home/new_admin/

## Installation Steps

1. **SSH login to root user on droplet server and navigated to working directory:**

```bash
ssh root@droplet-server_IPaddress
cd /opt
```

2. **Install Nexus as root user using wget:**

```bash
wget https://download.sonatype.com/nexus/3/nexus-3.81.1-01-linux-x86_64.tar.gz
```
