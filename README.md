# MULE SOFT PRACTICE

This practice shows some points about MuleSoft! 💻

 - Anypoint Studio 4 Linux
 - We have to extract the files from the downloaded site
 - If we use Ubuntu 20.04 just double tap in the Anypoint Studio 
 - Once made this , we just have to wait and Anypoint will init.
 - Select the defaulkt workspace / press Launch

## Link for Linux Instalation
`https://docs.mulesoft.com/studio/7.6/to-download-and-install-studio-lx`
    

## Using ANypointStudio to build an API / Testing it with Postman
  - As first step we have to create a new project 
  - After this , we give a name to our project and we can see our workspace 
  - Using an HTTP procotol we select the option in the right section and take a listener to our main section.
  - Then we select a payload to set it in the project and get a new Endpoind & asign it to our flow.
  - To run the project we just have to right click in the API building and tap run project / stop project
![](https://github.com/ddaniuwu/mule-soft-practice/blob/main/Captura%20de%20pantalla%20de%202021-10-12%2001-24-21.png)
## Testing with POSTMAN  🧪
  - To test it we just have to go POSTMAN and page the default URL in our request input.
  - http://0.0.0.0:8081/hellomule
- ![MulesoftTest](https://github.com/ddaniuwu/mule-soft-practice/blob/main/Captura%20de%20pantalla%20de%202021-10-12%2001-32-40.png)

## Setting a secure properties step 👩‍💻
- Once we made the process with de global elements configuration 
- We go to the scene and we drag an HTTP LIstener
![](https://github.com/ddaniuwu/mule-soft-practice/blob/main/Captura%20de%20pantalla%20de%202021-10-12%2008-43-33.png)

```
%dw 2.0
output application/json
---
[{
	FirstName: "Max",
	LastName: "Mule",
	Email: "maxthemule@mulesoft.com",
	Company: "MuleSoft"
}]

```
## Working with maven and Anypoint Studio
- One of the main functions working with maven / ANypoint Studio is that , it will packaged 
- our Anypoint project and then will prepare it for a deploy with cloudHUB or onpremise 

- Firstly we have to install maven in our computer / verify the prerequisites are correct .
- Here we have some references that could help us to install maven (Ubuntu 20.04)
- https://ubunlog.com/apache-maven-instalacion-ubuntu/  🤝

- Configuration with pom.xml 
- In our xml file , we have to add mule dependencies,as we can see in the next code.
```
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">
	<modelVersion>4.0.0</modelVersion>
	<groupId>org.mule.tools.maven</groupId>
	<artifactId>maven-tutorial</artifactId>
	<version>1.0.0-SNAPSHOT</version>
	<packaging>mule-application</packaging>
	<name>maven-tutorial</name>
	<properties>
		<project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
		<project.reporting.outputEncoding>UTF-8</project.reporting.outputEncoding>
		<app.runtime>4.3.0</app.runtime>
		<mule.maven.plugin.version>3.3.5</mule.maven.plugin.version>
	</properties>
	<build>
		<plugins>
			<plugin>
				<groupId>org.apache.maven.plugins</groupId>
				<artifactId>maven-clean-plugin</artifactId>
				<version>3.0.0</version>
			</plugin>
			<plugin>
				<groupId>org.mule.tools.maven</groupId>
				<artifactId>mule-maven-plugin</artifactId>
				<version>3.3.5</version>
				<extensions>true</extensions>
				<configuration>
				<cloudHubDeployment>
			      <muleVersion>4.3.0</muleVersion>
			      <username>ANYPOINT-PLATFORM-USERNAME-HERE</username>
			      <password>ANYPOINT-PLATFORM-PASSWORD-HERE</password>
			      <applicationName>mule-maven-project-tutorial</applicationName>
			      <environment>Sandbox</environment>   
			      <workers>1</workers>
			      <workerType>MICRO</workerType>
			      <properties>
				    <maven.compiler.target>1.8</maven.compiler.target>
				    <maven.compiler.source>1.8</maven.compiler.source>
				</properties>
			    </cloudHubDeployment>
				</configuration>
			</plugin>
		</plugins>
	</build>
	<dependencies>
        <dependency>
            <groupId>org.mule.connectors</groupId>
            <artifactId>mule-http-connector</artifactId>
            <version>1.5.17</version>
            <classifier>mule-plugin</classifier>
        </dependency>
        <dependency>
            <groupId>org.mule.connectors</groupId>
            <artifactId>mule-sockets-connector</artifactId>
            <version>1.1.6</version>
            <classifier>mule-plugin</classifier>
        </dependency>
	</dependencies>

	<repositories>
          <repository>
            <id>anypoint-exchange-v2</id>
            <name>Anypoint Exchange</name>
            <url>https://maven.anypoint.mulesoft.com/api/v2/maven</url>
            <layout>default</layout>
        </repository>
        <repository>
            <id>mulesoft-releases</id>
            <name>MuleSoft Releases Repository</name>
            <url>https://repository.mulesoft.org/releases/</url>
            <layout>default</layout>
        </repository>
    </repositories>
    <pluginRepositories>
        <pluginRepository>
            <id>mulesoft-releases</id>
            <name>mulesoft release repository</name>
            <layout>default</layout>
            <url>https://repository.mulesoft.org/releases/</url>
            <snapshots>
                <enabled>false</enabled>
            </snapshots>
        </pluginRepository>
    </pluginRepositories>
</project>
```

### PLUS
# Some issues presented in the process were resolved with tutorial videos :
- https://www.youtube.com/watch?v=zYBfGyhYRp8
- https://www.youtube.com/watch?v=oy1T2JGVXYQ&list=PLWk90omxsl2DFpjhWrHVy5vtkWy8XocyW

