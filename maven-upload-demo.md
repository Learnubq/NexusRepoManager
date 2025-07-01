# Maven Upload to Nexus

## Environment:
- Host: DigitalOcean Droplet (Ubuntu 24.10 x64)
- User: "nexus" (created manually)
- App: Java Maven Project


## Maven Setup in IDE:
**Built the JAR file on my local machine after setting up
- In pom.xml file in project directory, added a tag that lets me configure the repository for the snapshots in Nexus. This will allow Maven to find the repository and connect to it
  <distributionManagement>
        <snapshotRepository>
        <!--This is the ID you assign to the repository so you can identify it if you have a lot of that type of repository-->
            <id>nexus-snapshots</id>
            <!--This is the URL of the Nexus Maven snapshots repository-->
            <url>http://157.230.22.19:8081/repository/maven-snapshots/</url>
        </snapshotRepository>
        <!--Releases repository will have its own tag-->
    </distributionManagement>
- I then configured the user credentials for the Maven repository in the .m2 folder in my local machine user directory

```bash
ls -a | grep .m2
![m2](https://github.com/user-attachments/assets/c82d2299-972c-4897-b741-c20c43afcada)

  

## Steps to Upload JAR File to Nexus:
    
1. **Navigate to working project folder on local machine:**

```bash
cd java-app
ls
```

![gradle_build](https://github.com/user-attachments/assets/6acdbb8f-1cdb-4b1e-8726-0e5f45f9934c)

2. **Publish the JAR file to Nexus Repository:**

```bash
gradle publish
```

![Screenshot from 2025-07-01 15-16-05](https://github.com/user-attachments/assets/68bf920c-6845-4cea-ad48-9a98508ee29d)
