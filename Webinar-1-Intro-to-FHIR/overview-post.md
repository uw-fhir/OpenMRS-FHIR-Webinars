# An Introduction to the FHIR API

## Learning Objectives

1. Recognize the basic features and uses of modern **web APIs** & how **FHIR fits** in as a RESTful API.

2. Have a **general understanding** of the FHIR standard for health care data exchange, including an overview of the **history**, **purpose**, **scope**, the **adoption** and **implementation** situation.
    * Identify gaps between the spec and its implementations
    * Understand what functionality & features are **NOT** part of FHIR

3. Be aware of major projects, collaborations, implementations, and technologies that use or focus on FHIR (eg. HL7, SMART on FHIR, CDS Hooks, FHIR Bulk Data API, Argonaut,  etc. etc.)

4. Work through a simple Jupyter notebook FHIR tutorial that uses FHIR data to implement a simple healthcare risk score calculator for (BMI? )

5. Know where to access additional resources, readings, tutorials, communities and other related projects for further exploration of FHIR

6. Participate in an ideation session on opportuniites for FHIR in the OpenMRS community


## So, what is FHIR?

**FHIR** actually stands for **Fast** **Healthcare** **Interoperability** **Resources**, and, according to the [official summary](http://hl7.org/fhir/summary.html#2.17), is a

> "...next generation standards framework created by HL7. FHIR combines the best features of HL7's v2 , HL7 v3  and CDA  product lines while leveraging the **latest web standards** and applying a tight focus on **implementability**."
> 
>*source: http://hl7.org/fhir/summary.html#2.17*

So, if we want to understand the FHIR standard a bit better, we should dive a bit into what these `latest web standards` are and how they facilitate "implementability".

### FHIR: A RESTful API
(Summarize: Basically, FHIR is implemented as a RESTful API, in line with many such APIs around the internet. This summarizess the line above)

Now, you might wonder: what exactly is an API?

(* Basically, if some app/service is though of as a covered box, with lots of different machinery --> hard to add anything / build anything to work with / figure out what the machine really does
* But if your machine provides some sort of interface: connector that has documentation for available functionality of the connector --> allows interoperability
* Ideally, you have a universal connector: for example, usbs in many hardware applications; used by most devices, allows for easier interoperability
)

```
Placeholder for API diagram
```


APIs provide that sort of interface for services / apps / etc --> break down "official" definition

```
Placeholder for example APIs around the web: 
slack for example!
```

```
Link out to Slack #fhir analysis
```

### What about the RESTful Part?

The [official FHIR page](http://hl7.org/fhir/summary.html#2.17) introduces another major aspect of FHIR - **Resources** in the next paragraph:

> "FHIR solutions are built from a set of modular components called **Resources**...[that can] easily be assembled into working systems that solve real world clinical and administrative problems..."
> 
> *source: http://hl7.org/fhir/summary.html#2.17*

In short, resources represent differnt concepts used in healtcare: (patients, clinical encounters, medications, etc.)

- Quickly go over idea of resource, and of GET/PUT/POST/UPDATE

```
Link out to quick overview of resources
```

By modeling healthcare concepts as resources and providing? some standard functionality for using these resources, FHIR is essenitally a RESTful API in line with many such APIs out there

```
overview of APIs again, and a quick look at OpenMRS API
--> OpenMRS actually has an API (Is it restful?) --> quick overview of Restful Web Services
```

```
Link out to Pascal intro to APIs: https://psbrandt.io/fhir/
```

(Not sure where / how to discuss this: perhaps out of scope?) maybe only respond to possible questions about why we need FHIR.

(Perhaps tie in how being an API is not very useful; being an API with a specific focus/scope, large community, and good documentation is great)
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

```
Link out to Paste slides w/ what FHIR is / is not
```

### So, what is the FHIR API?
https://pasteapp.com/p/If8ttW55K0J/s/9mm9e825
https://pasteapp.com/p/If8ttW55K0J/s/EPMk15fruiV

## And, what is the FHIR API NOT?
https://pasteapp.com/p/If8ttW55K0J/s/8gw43cz9

## Main Gist: FHIR can be the electronic language of Healthcare 

--> Provides a General Framework for Healthcare Data and Standardized Methods to manipulate this data
--> Aims to cover ~80% of Healthcare situations (maybe comment on which "situations" apply
--> Provides a standard method for extension to cover the otehr 20%
  
Some Illustrations of This Concept
(Basically, show what fhir can do w/ different examples)

## Provides a foundation for a couple of differnet technologies
(Quuick run through, w/ a single phrase summary of what each tech is and how each tech uses FHIR)
SoF + App Galleries

CDS Hooks

Apple Health Kit

Illustrate with these examples

## Spec vs. Implementation

A standard is only useful if it is adopted

There's a large difference between the FHIR specifications and the actual implementation

1. Quick primer on the history of FHIR, including versions: https://www.hl7.org/fhir/history.html
2. Overview of adopted versions across some platforms: Apple Health, Azure, Epic, Cerner, a sandbox or two
3. Quick dive into other gaps between spec and implementation: page outlining get/post support

## A quick summary and critical look at FHIR in 2019

# Tutorial Runthrough

## To-Do
- [ ] Finish rough post outline w/ placeholders where necessary 
- [ ] Compare w/ ITECH presentation to identify any gaps
- [ ] Insert and check all out-links
- [ ] Compile a new slide-deck and insert slides into placeholders
- [ ] Do a quick run-through and fix issues (logical, spelling, links, tutorial, etc.)
- [ ] Publish Talk post by 7am 8/20
- [ ] Post to Slack