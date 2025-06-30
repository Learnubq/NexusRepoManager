# DigitalOcean Server User Setup

## Task: Create a new user on a freshly launched Ubuntu Droplet

### Environment:
- Host: DigitalOcean Droplet
- OS : Ubuntu 24.10 x64
- Access: Root via SSH

**Ensure the droplet server has 8GB of memory, 4 CPUs, and 160GB of storage (SSD) - the requirements needed to run Nexus on server are 4GB of memory, 2 CPUs, and 80GB of storage.
**Configure firewall to be accessible via port 22.

### Steps Performed:

1. **Created a new user named "nexus" on the droplet server and added to sudo group:**

```bash
adduser nexus
usermod -aG sudo nexus
```
2. **Installed Java version 17 on server as root user, because that is the version that works with Nexus:**

```bash
ssh root@droplet-server_IPaddress
