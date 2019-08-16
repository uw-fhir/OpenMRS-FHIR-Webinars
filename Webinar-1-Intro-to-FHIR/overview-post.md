- 


# An Introduction to the FHIR API

## Learning Objectives: 
1. Understand the basics about modern web APIs & how FHIR fits in as a RESTful API.
2. Have a general, foundational understanding of the FHIR spec, including an overview of the history, purpose, scope, the adoption and implementation situation. 
    *  Identify some gaps between the spec and implementations of the spec
    *  Understand what functionality / features are NOT included in FHIR, and what use cases the spec was NOT designed for
3. Recognize and know how and where to get more information on FHIR-related projects, efforts, etc. 
    *  FHIR website
    *  HL7, SMART, CDS Hooks, Argonaut, etc. etc. 
4. Work through a simple Jupyter notebook FHIR tutorial that loads data from an FHIR endpoint and uses it for some simple clinical decision support (eg., to calculate a Risk score)
5. Know where to access additional resources, readings, tutorials, communities and other related projects for further exploration of FHIR
6. Participate in an ideation session that includes topics like:
    What FHIR might enable in each participant’s work on OpenMRS 
    What barriers / issues / gaps might pop up
    Open Floor : other questions / ideas / comments


## What is FHIR?

### First , What is an API?

* Basically, if some app/service is though of as a covered box, with lots of different machinery --> hard to add anything / build anything to work with / figure out what the machine really does
* But if your machine provides some sort of interface: connector that has documentation for available functionality of the connector --> allows interoperability
* Ideally, you have a universal connector: for example, usbs in many hardware applications; used by most devices, allows for easier interoperability

APIs provide that sort of interface for services / apps / etc --> break down "official" definition

--> OpenMRS actually has an API --> quick overview of Restful Web Services

--> quickly highlight what the API might be lacking: 
- Not universal
- Lacking some documentation
- Lacking wider community use?


--> Go back to focus on FHIR:
scope is more general (Healthcare),
but:

Aim to provide a standard representation of healthcare records in all types of healthcare situations.

* In line with tech industry standards
* Buying from a wide range of stakeholders
* Adopted by HL7
* Bedrock for a number of related technologies

* Promissing!


--> Images of what FHIR is / is not w/ link to paste page

### So, what is the FHIR API?
https://pasteapp.com/p/If8ttW55K0J/s/9mm9e825
https://pasteapp.com/p/If8ttW55K0J/s/EPMk15fruiV

## And, what is the FHIR API NOT?
https://pasteapp.com/p/If8ttW55K0J/s/8gw43cz9

## Main Gist: FHIR can be the language of healthcare

- General Framework + Standardized  + Method for Extension
  
Some Illustrations of This Concept
(Basically, show what fhir can do w/ different examples)

SoF + App Galleries

CDS Hooks

Apple Health Kit

Illustrate with these examples


## Spec vs. Implementation

Have a general, foundational understanding of the FHIR spec (purpose, scope, current status, adoption/implementation situation (including gaps between spec and implementation)

## A Critical Look at FHIR in 2019