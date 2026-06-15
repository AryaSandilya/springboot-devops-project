# Spring PetClinic Sample Application [![Build Status](https://github.com/spring-projects/spring-petclinic/actions/workflows/maven-build.yml/badge.svg)](https://github.com/spring-projects/spring-petclinic/actions/workflows/maven-build.yml)[![Build Status](https://github.com/spring-projects/spring-petclinic/actions/workflows/gradle-build.yml/badge.svg)](https://github.com/spring-projects/spring-petclinic/actions/workflows/gradle-build.yml)

[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#https://github.com/spring-projects/spring-petclinic) [![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://github.com/codespaces/new?hide_repo_select=true&ref=main&repo=7517918)

## Understanding the Spring Petclinic application with a few diagrams


## Run Petclinic locally

Spring Petclinic is a [Spring Boot](https://spring.io/guides/gs/spring-boot) application built using [Maven](https://spring.io/guides/gs/maven/) or [Gradle](https://spring.io/guides/gs/gradle/).
Java 17 or later is required for the build, and the application can run with Java 17 or newer.

You first need to clone the project locally:

```bash
git clone https://github.com/spring-projects/spring-petclinic.git
cd spring-petclinic
```
If you are using Maven, you can start the application on the command-line as follows:

```bash
./mvnw spring-boot:run
```
With Gradle, the command is as follows:

```bash
./gradlew bootRun
```

You can then access the Petclinic at <http://localhost:8080/>.

<img width="1042" alt="petclinic-screenshot" src="https://cloud.githubusercontent.com/assets/838318/19727082/2aee6d6c-9b8e-11e6-81fe-e889a5ddfded.png">



## Database configuration

In its default configuration, Petclinic uses an in-memory database (H2) which
gets populated at startup with data. The h2 console is exposed at `http://localhost:8080/h2-console`,
and it is possible to inspect the content of the database using the `jdbc:h2:mem:<uuid>` URL. The UUID is printed at startup to the console.


### Prerequisites

The following items should be installed in your system:

- Java 17 or newer (full JDK, not a JRE)
- [Git command line tool](https://help.github.com/articles/set-up-git)
- Your preferred IDE
  - Eclipse with the m2e plugin. Note: when m2e is available, there is a m2 icon in `Help -> About` dialog. If m2e is
  not there, follow the installation process [here](https://www.eclipse.org/m2e/)
  - [Spring Tools Suite](https://spring.io/tools) (STS)
  - [IntelliJ IDEA](https://www.jetbrains.com/idea/)
  - [VS Code](https://code.visualstudio.com)

### Steps

1. On the command line run:

    ```bash
    git clone https://github.com/spring-projects/spring-petclinic.git
    ```

1. Inside Eclipse or STS:

    Open the project via `File -> Import -> Maven -> Existing Maven project`, then select the root directory of the cloned repo.

    Then either build on the command line `./mvnw generate-resources` or use the Eclipse launcher (right-click on project and `Run As -> Maven install`) to generate the CSS. Run the application's main method by right-clicking on it and choosing `Run As -> Java Application`.

1. Inside IntelliJ IDEA:

    In the main menu, choose `File -> Open` and select the Petclinic [pom.xml](pom.xml). Click on the `Open` button.

    - CSS files are generated from the Maven build. You can build them on the command line `./mvnw generate-resources` or right-click on the `spring-petclinic` project then `Maven -> Generates sources and Update Folders`.

    - A run configuration named `PetClinicApplication` should have been created for you if you're using a recent Ultimate version. Otherwise, run the application by right-clicking on the `PetClinicApplication` main class and choosing `Run 'PetClinicApplication'`.

1. Navigate to the Petclinic

    Visit [http://localhost:8080](http://localhost:8080) in your browser.

## Looking for something in particular?

|Spring Boot Configuration | Class or Java property files  |
|--------------------------|---|
|The Main Class | [PetClinicApplication](https://github.com/spring-projects/spring-petclinic/blob/main/src/main/java/org/springframework/samples/petclinic/PetClinicApplication.java) |
|Properties Files | [application.properties](https://github.com/spring-projects/spring-petclinic/blob/main/src/main/resources) |
|Caching | [CacheConfiguration](https://github.com/spring-projects/spring-petclinic/blob/main/src/main/java/org/springframework/samples/petclinic/system/CacheConfiguration.java) |

# Production Deployment & Monitoring Platform

## Overview

This project demonstrates an end-to-end DevOps implementation for deploying and monitoring a Spring Boot application on AWS EC2 using Jenkins, Docker, Prometheus, and Grafana.

The objective of this project is to automate application deployment through CI/CD pipelines and implement infrastructure monitoring for production-like environments.

---

## Architecture

GitHub Repository
↓
Jenkins CI/CD Pipeline
↓
Maven Build
↓
Docker Image Build
↓
Docker Container Deployment
↓
AWS EC2
↓
Node Exporter
↓
Prometheus
↓
Grafana Dashboard

---

## Technology Stack

### Cloud

* AWS EC2

### CI/CD

* Jenkins
* GitHub Webhooks

### Containerization

* Docker

### Application

* Java 17
* Spring Boot
* Spring PetClinic

### Monitoring

* Prometheus
* Node Exporter
* Grafana

### Operating System

* Ubuntu Linux

---

## Features

* Automated application build using Jenkins Pipeline
* Docker image creation and container deployment
* Continuous Integration through GitHub Webhooks
* Continuous Deployment on AWS EC2
* Infrastructure monitoring using Prometheus
* Real-time visualization using Grafana
* Linux server administration and service management

---

## Project Setup

### Clone Repository

```bash
git clone <repository-url>
cd springboot-devops-project
```

### Build Application

```bash
mvn clean package -DskipTests
```

### Build Docker Image

```bash
docker build -t petclinic:v1 .
```

### Run Container

```bash
docker run -d --name petclinic -p 8081:8080 petclinic:v1
```

---

## Jenkins Pipeline Stages

1. Source Code Checkout
2. Maven Build
3. Docker Image Build
4. Application Deployment
5. Continuous Delivery

---

## Monitoring Setup

### Node Exporter

Exposes infrastructure metrics such as:

* CPU Usage
* Memory Usage
* Disk Usage
* Network Statistics

### Prometheus

Responsible for:

* Metrics Collection
* Time Series Storage
* Monitoring Targets

### Grafana

Provides dashboards for:

* Server Health
* CPU Monitoring
* Memory Monitoring
* Filesystem Monitoring
* Network Monitoring

---

## Access URLs

| Service          | Port |
| ---------------- | ---- |
| Jenkins          | 8080 |
| Spring PetClinic | 8081 |
| Prometheus       | 9090 |
| Grafana          | 3000 |
| Node Exporter    | 9100 |

---

## Screenshots

### Jenkins Pipeline

Add screenshot here

### Application Deployment

Add screenshot here

### Prometheus Targets

Add screenshot here

### Grafana Dashboard

Add screenshot here

---

## Learning Outcomes

* CI/CD Pipeline Automation
* Docker Containerization
* AWS EC2 Administration
* Linux Service Management
* Infrastructure Monitoring
* DevOps Best Practices
* Jenkins Pipeline Development
* GitHub Webhook Integration

---

## Future Enhancements

* Kubernetes Deployment
* AWS EKS Integration
* Terraform Infrastructure Provisioning
* Nginx Reverse Proxy
* SSL/TLS Configuration
* Automated Rollback Strategy

---

## Author

Rahul Raj

DevOps Engineer | Java Backend Developer

LinkedIn: https://linkedin.com/in/rahul-raj-29a4b9120
