# simple-java-maven-app

This repository is for the
[Build a Java app with Maven](https://jenkins.io/doc/tutorials/build-a-java-app-with-maven/)
tutorial in the [Jenkins User Documentation](https://jenkins.io/doc/).

The repository contains a simple Java application which outputs the string 
"Hello world!" and is accompanied by a couple of unit tests to check that the
main application works as expected. The results of these tests are saved to a
JUnit XML report.

The `jenkins` directory contains an example of the `Jenkinsfile` (i.e. Pipeline)
you'll be creating yourself during the tutorial and the `jenkins/scripts` subdirectory
contains a shell script with commands that are executed when Jenkins processes
the "Deliver" stage of your Pipeline.

You can run the Jenkins pipeline using the Jenkinsfile inside the jenkins folder using a docker container. The commands to do so are listed below.

## Running the jenkins container 
```bash
docker run -d --name jenkins_pipeline -p 2000:8080 jenkins/jenkins:latest
```

## Execute a bash shell inside the running Jenkins container with root user privileges
```bash
docker exec -it --user root jenkins_pipeline /bin/bash
```

## Get the password to access Jenkins dashboard in http://localhost:2000/ by running the following command in the Jenkins bash shell
```bash
cat /var/jenkins_home/secrets/initialAdminPassword
```

## Install the required tools
```bash 
apt-get update
apt-get install -y
apt-get install -y openjdk-17-jdk
apt install maven
apt install apache2
```
## Check the maven version
```bash
mvn --version
```


