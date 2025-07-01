# Gradle Upload to Nexus

## Environment:
- Host: DigitalOcean Droplet (Ubuntu 24.10 x64)
- User: "nexus" (created manually)
- App: Java Gradle Project


## Gradle Setup in IDE:
**Built the JAR file on my local machine after setting up
- In build.gradle file in project directory, added a plugin for publishing a JAR to Maven formatted repository in Nexus Repository Manager
    apply plugin: 'maven-publish'
- Configured the JAR file that I was going to upload to Nexus Repository Manager - in publications section of build.gradle file
- Configured the name of the project in settings.gradle file that is in project directory - made it "my-app"
- Configured the Nexus repository I was going to upload the JAR file to e.g. the address of Nexus and the user credentials, in the repositories section of the build.gradle file
- Executed gradle build command in IDE terminal in project working directory - JAR file was created
  

## Steps to Upload JAR File to Nexus:
    
1. **Navigate to working project folder on local machine:**

```bash
cd java-app
```

![gradle_build](https://github.com/user-attachments/assets/6acdbb8f-1cdb-4b1e-8726-0e5f45f9934c)

2. **Publish the JAR file to Nexus Repository:**

```bash
gradle publish
```

![Screenshot from 2025-07-01 15-16-05](https://github.com/user-attachments/assets/68bf920c-6845-4cea-ad48-9a98508ee29d)


