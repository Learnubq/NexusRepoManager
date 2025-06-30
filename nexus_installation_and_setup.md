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

3. **Untarred the nexus .tar.gz file:**

```bash
tar -zxvf nexus-3.72.0-04-unix.tar.gz
clear
ls
```
**There was now a "nexus-3.72.0-04" folder and a "sonatype-work" folder.
![untarred](https://github.com/user-attachments/assets/b437114d-d9c2-4bf5-9ec0-b151197f0a22)



