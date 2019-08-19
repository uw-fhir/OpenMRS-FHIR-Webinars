# An Introduction to the FHIR API

## Learning Objectives

1. Recognize the basic features and uses of modern **web APIs** & how **FHIR fits** in as a RESTful API.

2. Have a **general understanding** of the FHIR standard for health care data exchange, including an overview of the **history**, **purpose**, **scope**, the **adoption** and **implementation** situation.
    * Identify gaps between the spec and its implementations
    * Understand what functionality & features are **NOT** part of FHIR

3. Be aware of major projects, collaborations, implementations, and technologies that use or focus on FHIR (eg. HL7, SMART on FHIR, CDS Hooks, FHIR Bulk Data API, Argonaut,  etc. etc.)

4. Work through a simple Jupyter notebook FHIR tutorial that uses FHIR data to implement a simple healthcare risk score calculator for (BMI? )

5. Know where to access additional resources, readings, tutorials, communities and other related projects for further exploration of FHIR

6. Participate in an ideation session on possible opportuniites for FHIR in the OpenMRS comunity


    *(   that includes topics like:
        What FHIR might enable in each participant’s work on OpenMRS 
        What barriers / issues / gaps might pop up
        Open Floor : other questions / ideas / comments
    )*

## So, what is FHIR?

**FHIR** actually stands for **Fast** **Healthcare** **Interoperability** **Resources**, and, according to the [official summary](http://hl7.org/fhir/summary.html#2.17), is a

> "...next generation standards framework created by HL7. FHIR combines the best features of HL7's v2 , HL7 v3  and CDA  product lines while leveraging the **latest web standards** and applying a tight focus on **implementability**."
> 
>*source: http://hl7.org/fhir/summary.html#2.17*

The official summary goes on to introduce FHIR **Resources** as
> a set of modular components... [that can] easily be assembled into working systems that solve real world clinical and administrative problems.



### First , What is an API?



* Basically, if some app/service is though of as a covered box, with lots of different machinery --> hard to add anything / build anything to work with / figure out what the machine really does
* But if your machine provides some sort of interface: connector that has documentation for available functionality of the connector --> allows interoperability
* Ideally, you have a universal connector: for example, usbs in many hardware applications; used by most devices, allows for easier interoperability

APIs provide that sort of interface for services / apps / etc --> break down "official" definition

What is a RESTful API?
(Link to pascal API intro?)
- Quickly go over idea of resource, and of GET/PUT/POST/UPDATE

--> OpenMRS actually has an API (Is it restful?) --> quick overview of Restful Web Services

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

1. Quick primer on the history of FHIR, including versions: https://www.hl7.org/fhir/history.html
2. Overview of adopted versions across some platforms: Apple Health, Azure, Epic, Cerner, a sandbox or two
3. Quick dive into other gaps between spec and implementation: page outlining get/post support

## A Critical Look at FHIR in 2019