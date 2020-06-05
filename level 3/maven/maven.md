# Maven
_Maven_  **is a powerful build tool for Java software projects.** 

 - downloading dependencies 
 -  compiling source code into binary code 
 - running tests  
 - packaging
 - deploying these artifacts to an application server
![enter image description here](http://tutorials.jenkov.com/images/maven/maven-overview-1.png)
 ## **Project Object Model**

The configuration of a Maven project is done via a  _Project Object Model (POM)_, represented by a  _pom.xml_  file. 
![enter image description here](https://i2.wp.com/www.dineshonjava.com/wp-content/uploads/2016/10/Maven-dirctory-structure.png?fit=220,298&ssl=1)

    <project>
        
        <modelVersion>4.0.0</modelVersion>
        <groupId>org.baeldung</groupId>
        <artifactId>org.baeldung</artifactId>
        <packaging>jar</packaging>
        <version>1.0-SNAPSHOT</version>
        <name>org.baeldung</name>
        <url>http://maven.apache.org</url>
        
        
        <dependencies>
            <dependency>
                <groupId>junit</groupId>
                <artifactId>junit</artifactId>
                <version>4.12</version>
                <scope>test</scope>
            </dependency>
        </dependencies>
       

        <build>
            <plugins>
                <plugin>
                //...
                </plugin>
            </plugins>
        </build>
        
    </project>
### **Project Identifiers**
-   _groupId_  – a unique base name of the company or group that created the project
-   _artifactId_  – a unique name of the project
-   _version_  – a version of the project
-   _packaging_  – a packaging method (e.g.  _WAR_/_JAR_/_ZIP_)
### **Dependencies**
These external libraries that a project uses are called dependencies. The dependency management feature in Maven ensures automatic **download of those libraries from a central repository, so you don't have to store them locally.**

    <dependency>
        <groupId>org.springframework</groupId>
        <artifactId>spring-core</artifactId>
        <version>4.3.5.RELEASE</version>
    </dependency>

### **Repositories**

**A repository in Maven is used to hold build artifacts and dependencies of varying types.** The default local repository is located in the  _.m2/repository_  folder under the home directory of the user.

    <repositories>
        <repository>
            <id>JBoss repository</id>
            <url>http://repository.jboss.org/nexus/content/groups/public/</url>
        </repository>
    </repositories>
### **Properties**

Custom properties can help to make your  _pom.xml_  file easier to read and maintain.

    <properties>
        <spring.version>4.3.5.RELEASE</spring.version>
    </properties>
     
    <dependencies>
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-core</artifactId>
            <version>${spring.version}</version>
        </dependency>
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-context</artifactId>
            <version>${spring.version}</version>
        </dependency>
    </dependencies>
### **Build**

    <build>
        <defaultGoal>install</defaultGoal>
        <directory>${basedir}/target</directory>
        <finalName>${artifactId}-${version}</finalName>
        <filters>
          <filter>filters/filter1.properties</filter>
        </filters>
        //...
    </build>
### **Using  _Profiles_**

Another important feature of Maven is its support for  _profiles._  A  _profile_  is basically a set of configuration values.

    <profiles>
        <profile>
            <id>production</id>
            <build>
                <plugins>
                    <plugin>
                    //...
                    </plugin>
                </plugins>
            </build>
        </profile>
        <profile>
            <id>development</id>
            <activation>
                <activeByDefault>true</activeByDefault>
            </activation>
            <build>
                <plugins>
                    <plugin>
                    //...
                    </plugin>
                </plugins>
            </build>
         </profile>
     </profiles>
the default profile is set to  _development_. If you want to run the  _production_ _profile_, you can use the following Maven command:

`mvn clean` `install` `-Pproduction`
## **Maven Build Lifecycles**
The following list shows the most important Maven  _lifecycle_  phases:

-   _validate_  – checks the correctness of the project
-   _compile_  – compiles the provided source code into binary artifacts
-   _test_  – executes unit tests
-   _package_  – packages compiled code into an archive file
-   _integration-test_  – executes additional tests, which require the packaging
-   _verify_  – checks if the package is valid
-   _install_  – installs the package file into the local Maven repository
-   _deploy_  – deploys the package file to a remote server or repository

**A Maven plugin**
 is a collection of one or more goals. Goals are executed in phases, which helps to determine the order in which the goals are executed.

## Generating a Simple Java Project



    mvn archetype:generate
      -DgroupId=org.baeldung
      -DartifactId=org.baeldung.java 
      -DarchetypeArtifactId=maven-archetype-quickstart
      -DinteractiveMode=false

**Compiling and Packaging a Project**

    mvn compile

Maven will run through all lifecycle phases needed by the compile phase to build the project's sources. If you want to run only the test phase, you can use:

    mvn test

## Executing an Application

Finally, we are going to execute our Java project with the exec-maven-plugin. Let's configure the necessary plugins in the pom.xml:


    <build>
        <sourceDirectory>src</sourceDirectory>
        <plugins>
            <plugin>
                <artifactId>maven-compiler-plugin</artifactId>
                <version>3.6.1</version>
                <configuration>
                    <source>1.8</source>
                    <target>1.8</target>
                </configuration>
            </plugin>
            <plugin>
                <groupId>org.codehaus.mojo</groupId>
                <artifactId>exec-maven-plugin</artifactId>
                <version>1.5.0</version>
                <configuration>
                    <mainClass>org.baeldung.java.App</mainClass>
                </configuration>
            </plugin>
        </plugins>
    </build>

The first plugin, maven-compiler-plugin, is responsible for compiling the source code using Java version 1.8. The exec-maven-plugin searches for the mainClass in our project.

To execute the application, we run the following command:

    mvn exec:java
