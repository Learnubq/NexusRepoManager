# Gradle Upload to Nexus

## Environment:
- Host: DigitalOcean Droplet (Ubuntu 24.10 x64)
- User: "nexus" (created manually)
- App: Java Gradle Project


## Gradle Setup in IDE
**Built the JAR file on my local machine after setting up
- In build.gradle file in project directory, added a plugin for publishing a JAR to Maven formatted repository in Nexus Repository Manager
    apply plugin: 'maven-publish'
- Configured the JAR file that I was going to upload to Nexus Repository Manager - in publications section of build.gradle file
- Configured the name of the project in settings.gradle file that is in project directory - made it "my-app"
- Configured the Nexus repository I was going to upload the JAR file to e.g. the address of Nexus and the user credentials, in the repositories section of the build.gradle file


    
