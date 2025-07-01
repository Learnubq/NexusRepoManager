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
            <url>http://<repoIPaddress>:8081/repository/maven-snapshots/</url>
        </snapshotRepository>
        <!--Releases repository will have its own tag-->
    </distributionManagement>
- I then configured the user credentials for the Maven repository in the .m2 folder in my local machine user directory
- I then added the following plugins to deploy to Maven repo
  <plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-deploy-plugin</artifactId>
    <version>3.1.1</version>
  </plugin>

  <plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-deploy-plugin</artifactId>
  </plugin>


```bash
ls -a | grep .m2
ls .m2
cd .m2
ls
vim settings.xml
```
**Added this code to the editor
  <settings>
  <servers>
    <server>
      <id>nexus-snapshots</id>
      <username>Najee</username>
      <password>MyPassword</password>
    </server>
  </servers>
</settings>

- Navigated to the java-maven-app project directory and executed command
```bash
mvn package
```
**There was now a target directory within the project directiory

![mvnpackage](https://github.com/user-attachments/assets/6f5825a4-c588-4217-bce2-9e0ca58fb782)

**The JAR file was in the target directory

```bash
ls target
```

![JARmvnpackage](https://github.com/user-attachments/assets/9e0a4baf-6ecc-4d2d-98ac-198a13c9866f)


## Steps to Upload JAR File to Nexus:
    
1. **Navigate to working project folder on local machine:**

```bash
mvn deploy
```
