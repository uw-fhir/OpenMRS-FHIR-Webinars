# An Introduction to the FHIR API

## Learning Objectives

1. Recognize the basic features and uses of modern **web APIs** & how **FHIR fits** in as a RESTful API.

2. Have a general **understanding** of the FHIR standard for health care data exchange, including an overview of the **history**, **purpose**, **scope**, the **adoption** and **implementation** situation.
    * Identify gaps between the spec and its implementations
    * Understand what functionality & features are **NOT** part of FHIR

3. Have a general **awareness** of major **projects**, **collaborations**, **implementations**, and **technologies** that use or focus on FHIR.

4. Work through a FHIR tutorial that **queries** data from a **FHIR endpoint** to implement a simple cardiovascular risk calculator.

5. Be able to explore FHIR independently through provided access to **projects**, **readings**, **tutorials**, and other useful resources

6. Participate in an **ideation session** on opportunities for **FHIR** in the **OpenMRS** community


## So, what is FHIR?

**FHIR** stands for **Fast** **Healthcare** **Interoperability** **Resources**.

According to the [summary in the official documentation](http://hl7.org/fhir/summary.html#2.17), 

FHIR is a
> "...next generation standards framework created by HL7. FHIR combines the best features of HL7's v2 , HL7 v3  and CDA  product lines while leveraging the **latest web standards** and applying a tight focus on **implementability**."
> 
>*source: http://hl7.org/fhir/summary.html#2.17*

## If FHIR is "next generation", what came before?

The summary above does not paint a very comprehensive picture of the major health data standards maintained by the [HL7 Organization](http://www.hl7.org/about/index.cfm?ref=nav) before FHIR. If you're interested in a more thorough history lesson about the **HL7 V2, V3, and CDA** standards, let us know. You can also check out these two slide deck and walk-through - and again, send us any questions you might have!

https://pasteapp.com/p/Ggufyqh11of/s/5m7aiy75
https://pasteapp.com/p/If8ttW55K0J/s/4q19rk20


The main takeaway: previous HL7 standards are still in use today to varying degrees, but FHIR has seen very fast growth and adoption. 

https://github.com/bhi-spring-591-2019/instructors/blob/master/HL7%20and%20XDSToolkit%20walkthrough.md

https://www.healthit.gov/buzz-blog/interoperability/heat-wave-the-u-s-is-poised-to-catch-fhir-in-2019


## What about the "web standards" part of the summary?

To understand FHIR better, we'll dive into what the aformentioned `latest web standards` are, how they facilitate `implementability`, and what this `implementability` could mean.

The key point to remember is: FHIR is a **RESTful API**, which puts it in a class of web standards that is very widely used in the tech field to transfer all kinds of data between different applications and systems. 

Some examples you might be familiar with: the [Twitter Search API](https://developer.twitter.com/en/docs/tweets/search/quick-start/premium-30-day), the [Github API](https://developer.github.com/v3/), [IBM's Watson Assistant](https://developer.ibm.com/patterns/watson-conversation-with-ibm-linuxone-systems/) and countless other services provide access to their data through a RESTful API. 

(Slack also has a REST API that you can easily play with - I started doing an analysis of the OpenMRS #fhir channel here if you're interested: https://github.com/pmanko/slack_analysis/blob/master/fhir_channel.ipynb)

### So, FHIR is a RESTful API

But what does that actually mean? 

We'll look into the **RESTful** part later, but first lets focus on APIs, or Application Programming Interfaces.



e think of an application - any application you can think of - as a hidden box
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

https://www.hl7.org/fhir/resourcelist.html
https://www.hl7.org/fhir/operationslist.html#1.5


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

**
(eg. HL7, SMART on FHIR, CDS Hooks, FHIR Bulk Data API, Argonaut,  etc. etc.)**

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



## Tutorial Runthrough
https://github.com/uw-fhir/fhir-api-tutorial/blob/master/fhir-calculator-notebook.ipynb

## Explore on your own!
(modified version of https://uw-fhir.github.io/FHIRupUW/)

### Advanced FHIR Topics
https://pasteapp.com/p/If8ttW55K0J/s/dcbcl3wi


## To-Do
- [ ] Finish rough post outline w/ placeholders where necessary 
- [x] Compare w/ ITECH presentation to identify any gaps
- [ ] Insert and check all out-links
- [ ] Compile a new slide-deck and insert slides into placeholders
- [ ] Do a quick run-through and fix issues (logical, spelling, links, tutorial, etc.)
- [ ] Publish Talk post by 7am 8/20
- [ ] Post to Slack


