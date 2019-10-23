# Technical Review of the OpenMRS FHIR Module

https://github.com/openmrs/openmrs-module-fhir

- [Technical Review of the OpenMRS FHIR Module](#technical-review-of-the-openmrs-fhir-module)
  - [Architecture](#architecture)
    - [OpenMRS and OpenMRS Modules](#openmrs-and-openmrs-modules)
    - [The FHIR Module](#the-fhir-module)
  - [External Dependencies](#external-dependencies)
    - [HAPI FHIR Libraries](#hapi-fhir-libraries)

## Architecture

### OpenMRS and OpenMRS Modules
http://devmanual.openmrs.org/en/Technology/architecture.html 

http://devmanual.openmrs.org/en/Technology/architecture.html#the-modular-architecture

![OpenMRS Architecture](OpenMRS-architecture.png)

**OpenMRS Data Model**
![OpenMRS Data Model](https://wiki.openmrs.org/download/attachments/589829/openmrs_data_model_1.9.0.png?version=3&modificationDate=1339449402000&api=v2)

**Hibernate**
- Object-Relational Mapping
  
**Spring**
Application development framework
- support MVC model 
- Aspect-oriented programming
  
**Presentation**

*Reference Application UI* 
https://github.com/openmrs/openmrs-distro-referenceapplication

*Microfrontends UI*
https://github.com/openmrs/openmrs-rfc-frontend/tree/master/text

---

### The FHIR Module
https://wiki.openmrs.org/display/projects/OpenMRS+FHIR+Module
https://wiki.openmrs.org/display/projects/OpenMRS+FHIR+Module+Architecture

Conformance Statement: https://openmrs-spa.org/openmrs/ws/fhir/metadata

**Overview and Strategy Pattern**
https://wiki.openmrs.org/display/projects/FHIR+Strategy+Pattern

![FHIR Module Architecture](fhir-module-diagram-1.png)

**Rollout Plan**

![FHIR Module Architecture](fhir-module-diagram-2-1.png)
![FHIR Module Architecture](fhir-module-diagram-2-2.png)
![FHIR Module Architecture](fhir-module-diagram-2-3.png)

**Current situation vs. Potential Outcome**

![FHIR Module Architecture](fhir-module-diagram-3.png)

**Smart on FHIR Model**

![FHIR Module Architecture](fhir-module-diagram-4.png)

## External Dependencies

### HAPI FHIR Libraries

**FHIR Base**
https://mvnrepository.com/artifact/ca.uhn.hapi.fhir/hapi-fhir-base/3.1.0 **2.5**

**FHIR Structures**
https://mvnrepository.com/artifact/ca.uhn.hapi.fhir/hapi-fhir-structures-dstu3/1.4

https://mvnrepository.com/artifact/ca.uhn.hapi.fhir/hapi-fhir-structures-dstu3/2.5?

**Validation**
https://github.com/jamesagnew/hapi-fhir/tree/master/hapi-fhir-validation-resources-dstu3


