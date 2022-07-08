# Getting started of Spring project in VSCode

A minimal example of Spring Maven in VSCode


## Setup Java JDK
1. Download Java JDK
 - https://github.com/redhat-developer/vscode-java/wiki/JDK-Requirements#java.configuration.runtimes
 - https://adoptium.net/

2. Set windows user environment variable. If any permission issue, set it as an environment variable
```
JAVA_HOME = path\to\your\Eclipse Adoptium\jdk-17.0.3.7-hotspot
```

3. Install various vscode marketplace Java extensions


## Setup Project

Following this tutorial
https://code.visualstudio.com/docs/java/java-project

1. Use crtl shift P: Spring initializr > Maven > ver xx > Java ver yy > com.example > demo > jar 

2. Save vscode workspace demo.code-workspace in the same folde as pom.xml


## FAQ

### Q1. Error on Maven > site
java.lang.NoClassDefFoundError: org/apache/maven/doxia/siterenderer/DocumentContent

Try add plugins in your <build/>. Add these:
```
<build>
  <plugins>
    <plugin>
      <groupId>org.apache.maven.plugins</groupId>
      <artifactId>maven-site-plugin</artifactId>
      <version>3.10.0</version>
    </plugin>

    <plugin>
      <groupId>org.apache.maven.plugins</groupId>
      <artifactId>maven-project-info-reports-plugin</artifactId>
      <version>3.2.1</version>
    </plugin>
  </plugins>
</build>
```

### Q2. Error on Maven > deploy
Failed to execute goal org.apache.maven.plugins:maven-deploy-plugin:2.8.2:deploy (default-deploy) on project demo: Deployment failed: repository element was not specified in the POM inside distributionManagement element or in -DaltDeploymentRepository=id::layout::url parameter 

