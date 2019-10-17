
*Check out the [Webinars Github Page](https://github.com/uw-fhir/OpenMRS-FHIR-Webinars/) for another view of these tutorial*\

# Webinar 3 - OpenMRS Dev Setup for FHIR Module and Microfrontends


Video Tutorial: (coming soon)


## Outline
- [Webinar 3 - OpenMRS Dev Setup for FHIR Module and Microfrontends](#webinar-3---openmrs-dev-setup-for-fhir-module-and-microfrontends)
  - [Outline](#outline)
  - [Overview](#overview)
  - [Learning Objectives](#learning-objectives)
  - [Referenced Resources](#referenced-resources)
  - [OpenMRS Architecture Overview](#openmrs-architecture-overview)
    - [OpenMRS Modules](#openmrs-modules)
      - [FHIR Module](#fhir-module)
      - [SPA Module](#spa-module)
  - [Microfrontends Architecture Overview](#microfrontends-architecture-overview)
    - [Import Map](#import-map)
    - [Frontend Javascript Modules (ESM)](#frontend-javascript-modules-esm)
  - [The Full Picture](#the-full-picture)
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

---

## Learning Objectives

1. Gain a birds-eye view understanding of the OpenMRS reference application architecture.
2. Understand how the FHIR Module is integrated into the RefApp distribution.
3. Understand how the MF project integrates into the OpenMRS distribution.
4. Set up a local dev environment for working on the FHIR module using the OpenMRS SDK.
5. Set up a local dev environment for MF ESM modules.

---

## Referenced Resources

--- 

## OpenMRS Architecture Overview

- OpenMRS core + modules

### OpenMRS Modules

#### FHIR Module

#### SPA Module

## Microfrontends Architecture Overview

### Import Map

### Frontend Javascript Modules (ESM)

## The Full Picture

** What we would like to have on our local dev machine:**

- An OpenMRS server running the latest openMRS RefApp distribution.
- A cloned FHIR module codebase that is compiled locally and used by the OpenMRS server.
- A cloned SPA module codebase that is compiled locally and used by the OpenMRS server.
- Cloned codebases for the FHIR and Home Microfrontend javascript modules that compile and are served up locally, and connect to the OpenMRS server using the mentioned SPA module. 

** Visual End Goal: **


## To-Do
- [ ] Post to Github and OpenMRS Talk
- [ ] Schedule time for an OpenMRS webinar on this topic

-----------------
## Notes


--- 


### Wikis etc:
- http://booki.flossmanuals.net/openmrs-guide/
- Read http://write.flossmanuals.net/openmrs-developers-guide/welcome-to-openmrs/
- https://wiki.openmrs.org/display/docs/Implementer+Documentation

OpenMRS Core: Oldschool Standard Java App in Tomcat w/ use of Spring (inversion of control, AOP)
--> requires modules to provide any
--> works well because

OpenMRS Reference App: Core + a standard set of modules

A Distribution: Core + a use-case specific set of modules

### Installing OpenMRS:
- For development: https://wiki.openmrs.org/display/docs/OpenMRS+SDK

https://wiki.openmrs.org/display/docs/Developer+How-To+Setup+And+Use+IntelliJ



#### 1. Install Java

#### 2. Install Maven

#### 3. Install IntelliJ 

#### 4. Install the OpenMRS SDK

`mvn openmrs-sdk:setup -DserverId=openmrs-spa -Ddistro=referenceapplication:2.9.0 -DdbUri=jdbc:mysql://localhost:3306/openmrs-spa -DdbUser=openmrs -DdbPassword=openmrs"`

### Microfrontends
https://talk.openmrs.org/t/an-amazing-future-for-openmrs/22328
https://github.com/openmrs/openmrs-module-spa/tree/initial-java-module
 