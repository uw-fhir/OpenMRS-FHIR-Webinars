# Technical Review of the OpenMRS FHIR Module

https://github.com/openmrs/openmrs-module-fhir

- [Technical Review of the OpenMRS FHIR Module](#technical-review-of-the-openmrs-fhir-module)
  - [Architecture](#architecture)
    - [OpenMRS and OpenMRS Modules](#openmrs-and-openmrs-modules)
    - [The FHIR Module](#the-fhir-module)
      - [Architecture Diagrams](#architecture-diagrams)
      - [Code Study: Serving a Patient Resource](#code-study-serving-a-patient-resource)

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

#### Architecture Diagrams

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

#### Code Study: Serving a Patient Resource

1. https://github.com/openmrs/openmrs-module-fhir/tree/master/api/src/main/java/org/openmrs/module/fhir/api

2. https://github.com/openmrs/openmrs-module-fhir/blob/master/api/src/main/java/org/openmrs/module/fhir/api/util/FHIRPatientUtil.java

3. Compare https://hapifhir.io/apidocs-dstu3/org/hl7/fhir/dstu3/model/Patient.html and http://hl7.org/fhir/STU3/patient.html

4. https://github.com/openmrs/openmrs-module-fhir/blob/master/api/src/main/java/org/openmrs/module/fhir/api/strategies/patient/PatientStrategy.java
   