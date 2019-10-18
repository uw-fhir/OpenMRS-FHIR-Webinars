
*Check out the [Webinars Github Page](https://github.com/uw-fhir/OpenMRS-FHIR-Webinars/) for another view of these tutorial*\

# Webinar 3 - OpenMRS Dev Setup for FHIR Module and Microfrontends


Video Tutorial: (coming soon)


## Outline
- [Webinar 3 - OpenMRS Dev Setup for FHIR Module and Microfrontends](#webinar-3---openmrs-dev-setup-for-fhir-module-and-microfrontends)
  - [Outline](#outline)
  - [Overview](#overview)
  - [Learning Objectives](#learning-objectives)
  - [Referenced Resources](#referenced-resources)
  - [- https://talk.openmrs.org/t/micro-frontends-architecture-for-openmrs/22557](#httpstalkopenmrsorgtmicro-frontends-architecture-for-openmrs22557)
  - [OpenMRS Architecture Overview](#openmrs-architecture-overview)
    - [OpenMRS Modules](#openmrs-modules)
      - [FHIR Module](#fhir-module)
      - [SPA Module](#spa-module)
  - [Microfrontends Architecture Overview](#microfrontends-architecture-overview)
    - [Import Map and Frontend Javascript Modules (ESM)](#import-map-and-frontend-javascript-modules-esm)
  - [The Full Picture](#the-full-picture)
  - [Walkthrough Tutorial](#walkthrough-tutorial)
    - [1. Install Dependencies](#1-install-dependencies)
    - [2. Clone Relevant Codebases](#2-clone-relevant-codebases)
    - [3. Set up OpenMRS RefApp](#3-set-up-openmrs-refapp)
  - [Screenshots](#screenshots)
  - [To-Do](#to-do)
  - [Notes](#notes)
    - [Wikis etc:](#wikis-etc)
    - [Installing OpenMRS:](#installing-openmrs)
      - [1. Install Java](#1-install-java)
      - [2. Install Maven](#2-install-maven)
      - [3. Install IntelliJ](#3-install-intellij)
      - [4. Install the OpenMRS SDK](#4-install-the-openmrs-sdk)
    - [Microfrontends](#microfrontends)

---

## Overview
This tutorial will be focused on setting up a local development environment using the OpenMRS SDK. The approach can be generalized for work on any existing or new OpenMRS modules, but for this tutorial we will focus on the FHIR module and the Microfrontends Project. The MF project includes an OpenMRS module that allows OpenMRS to support the client-side SPA-based frontend to OpenMRS. 

Please feel free to send feedback / suggestions for improving this tutorial! This content is based on the availble documentation along with vital input from @psbrandt, and we're definitely looking to improve it with input from the community.

*Note: We won't focus on implementation-specific installation and setup that 
might concern you for deploying production-ready solutions. See the Implementers Guide for guidance on that.*


**End Goal**

You should be able to see the following screens after a successful setup, all running off of the local machine:

![OpenMRS SPA Login](webinar-3-openmrs-spa-login.png)


[(click here for full set of screenshots)](#screenshots)


---

## Learning Objectives

1. Gain a birds-eye view understanding of the OpenMRS reference application architecture.
2. Understand how the FHIR Module is integrated into the RefApp distribution.
3. Understand how the MF project integrates into the OpenMRS distribution.
4. Set up a local dev environment for working on the FHIR module using the OpenMRS SDK.
5. Set up a local dev environment for MF ESM modules.

---

## Referenced Resources
- http://devmanual.openmrs.org/en/Technology/getSetUp.html
- https://wiki.openmrs.org/display/projects/Setup+local+development+environment+for+OpenMRS+SPA
- https://wiki.openmrs.org/pages/viewpage.action?pageId=224527568
- https://talk.openmrs.org/t/micro-frontends-architecture-for-openmrs/22557
--- 

## OpenMRS Architecture Overview
http://devmanual.openmrs.org/en/Technology/architecture.html

### OpenMRS Modules

#### FHIR Module

#### SPA Module

## Microfrontends Architecture Overview
https://talk.openmrs.org/t/an-amazing-future-for-openmrs/22328
- https://talk.openmrs.org/t/micro-frontends-architecture-for-openmrs/22557

### Import Map and Frontend Javascript Modules (ESM)
https://wiki.openmrs.org/display/projects/Frontend+Implementer+Documentation

## The Full Picture

** What we would like to have on our local dev machine:**

- An OpenMRS server running the latest openMRS RefApp distribution.
- A cloned FHIR module codebase that is compiled locally and used by the OpenMRS server.
- A cloned SPA module codebase that is compiled locally and used by the OpenMRS server.
- Cloned codebases for the FHIR and Home Microfrontend javascript modules that compile and are served up locally, and connect to the OpenMRS server using the mentioned SPA module. 

## Walkthrough Tutorial
http://devmanual.openmrs.org/en/Technology/getSetUp.html
https://wiki.openmrs.org/display/projects/Setup+local+development+environment+for+OpenMRS+SPA

### 1. Install Dependencies

**Java**

Install JDK 8:
https://docs.oracle.com/javase/8/docs/technotes/guides/install/install_overview.html

```
> java -version

java version "1.8.0_221"
Java(TM) SE Runtime Environment (build 1.8.0_221-b11)
Java HotSpot(TM) 64-Bit Server VM (build 25.221-b11, mixed mode)
```
**Maven**

Install Maven:
http://maven.apache.org/guides/getting-started/maven-in-five-minutes.html

```
mvn --version

Apache Maven 3.6.2 (40f52333136460af0dc0d7232c0dc0bcf0d9e117; 2019-08-27T08:06:16-07:00)
Maven home: C:\lib\apache-maven-3.6.2\bin\..
Java version: 1.8.0_221, vendor: Oracle Corporation, runtime: C:\java\jdk1.8.0_221\jre
Default locale: en_US, platform encoding: Cp1252
OS name: "windows 10", version: "10.0", arch: "amd64", family: "windows"
```

**OpenMRS SDK**

http://devmanual.openmrs.org/en/Technology/getSetUp.html#download-and-install
https://wiki.openmrs.org/display/docs/OpenMRS+SDK#OpenMRSSDK-Setup
https://wiki.openmrs.org/display/docs/OpenMRS+SDK+Step+By+Step+Tutorials

```
mvn org.openmrs.maven.plugins:openmrs-sdk-maven-plugin:setup-sdk
mvn openmrs-sdk:help

[INFO] Scanning for projects...
.
.
.
OpenMRS SDK 3.13.2

For more info, see SDK documentation: https://wiki.openmrs.org/display/docs/OpenMRS+SDK
```

### 2. Clone Relevant Codebases

**OpenMRS FHIR Module**
`git clone https://github.com/openmrs/openmrs-module-fhir.git`

**OpenMRS SPA Module**
`git clone https://github.com/openmrs/openmrs-module-spa.git`

**Javascript Modules**

In this example, we will clone the `openmrs-esm-home` and the `openmrs-esm-api` codebases, but feel free to choose whichever `openmrs-esm-*` projects you'd like.

```
git clone https://github.com/openmrs/openmrs-esm-api.git
git clone https://github.com/openmrs/openmrs-esm-home.git
```

### 3. Set up OpenMRS RefApp

We will use the *OpenMRS SDK* to create a local development server running the OpenMRS Reference Application Distribution.






## Screenshots
![OpenMRS Login](webinar-3-openmrs-login.png)

![OpenMRS Admin](webinar-3-openmrs-admin.png)

![OpenMRS Modules](webinar-3-openmrs-modules.png) 

![OpenMRS SPA Login](webinar-3-openmrs-spa-login.png)

![OpenMRS SPA Home](webinar-3-openmrs-spa-home.png)

![OpenMRS SPA ESM](webinar-3-openmrs-spa-esm.png)

## To-Do
- [ ] Post to Github and OpenMRS Talk
- [ ] Schedule time for an OpenMRS webinar on this topic

-----------------
## Notes


--- 


### Wikis etc:
- http://om.rs/guide
- http://om.rs/devmanual

OpenMRS Core:
Standard Java App in Tomcat w/ use of Spring

OpenMRS Reference App: Core + a standard set of modules

A Distribution: Core + a use-case specific set of modules

### Installing OpenMRS:
- For development: http://om.rs/devmanual

https://wiki.openmrs.org/display/docs/Developer+How-To+Setup+And+Use+IntelliJ

#### 1. Install Java

#### 2. Install Maven

#### 3. Install IntelliJ 

#### 4. Install the OpenMRS SDK

`mvn openmrs-sdk:setup -DserverId=openmrs-spa -Ddistro=referenceapplication:2.9.0 -DdbUri=jdbc:mysql://localhost:3306/openmrs-spa -DdbUser=openmrs -DdbPassword=openmrs"`

### Microfrontends
https://talk.openmrs.org/t/an-amazing-future-for-openmrs/22328
https://github.com/openmrs/openmrs-module-spa/tree/initial-java-module
 