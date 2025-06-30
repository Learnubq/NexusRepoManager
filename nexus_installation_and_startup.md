![ls](https://github.com/user-attachments/assets/69347cf4-2e9b-4234-ace7-dd52ae45914d)# Nexus Installation on Droplet Server

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
tar -zxvf nexus-3.81.1-01-linux-x86_64.tar.gz
clear
ls
```
**There was now a "nexus-3.81.1-01" folder and a "sonatype-work" folder.
![untarred](https://github.com/user-attachments/assets/b437114d-d9c2-4bf5-9ec0-b151197f0a22)

4. **Checked permissions of the "nexus-3.81.1-01" folder and the "sonatype-work" folder. Changed their root user and root group ownership to nexus user and nexus group ownership(so I could run the Nexus application as the nexus user):**

```bash
ls -l
chown -R nexus:nexus nexus-3.81.1-01
chown -R nexus:nexus sonatype-work
ls -l
```
**There was now a nexus user and nexus group ownership assigned to the "nexus-3.81.1-01" and "sonatype-work" folders. So I could execute the application in the nexus-3.81.1-01 folder and access the sonatype-work folder to execute tasks on it.
![ls](https://github.com/user-attachments/assets/61214fd4-5837-4ead-b323-f6793f8bec39)

5. **Set Nexus configuration so that I could run it as "nexus" user:**

```bash
vim nexus-3.81.1-01/bin/nexus.rc
run_as_user="nexus"
ESC
:WQ
su - nexus
/opt/nexus-3.81.1-01/bin/nexus start
```
![startnexus](https://github.com/user-attachments/assets/f00a489c-1367-4861-a661-3efad755381a)

6. **Then checked that Nexus app was running and checked the port it was running on using its process ID:**

```bash
ps aux | grep nexus
netstat -lnpt
```





