# An Introduction to the FHIR API

## Outline
- [An Introduction to the FHIR API](#an-introduction-to-the-fhir-api)
  - [Outline](#outline)
  - [Learning Objectives](#learning-objectives)
  - [So, what is FHIR?](#so-what-is-fhir)
  - [Provides a foundation for a couple of differnet technologies](#provides-a-foundation-for-a-couple-of-differnet-technologies)
  - [Spec vs. Implementation](#spec-vs-implementation)
  - [A quick summary and critical look at FHIR in 2019](#a-quick-summary-and-critical-look-at-fhir-in-2019)
  - [Tutorial Runthrough](#tutorial-runthrough)
  - [Explore on your own!](#explore-on-your-own)
    - [Advanced FHIR Topics](#advanced-fhir-topics)
  - [To-Do](#to-do)
  - [Notes and Edits](#notes-and-edits)

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

According to the [summary in the official documentation](http://hl7.org/fhir/summary.html#2.17), FHIR is a
> "...next generation standards framework created by HL7. FHIR combines the best features of HL7's v2 , HL7 v3  and CDA  product lines while leveraging the **latest web standards** and applying a tight focus on **implementability**."
> 
>*source: http://hl7.org/fhir/summary.html#2.17*

**If FHIR is "next generation", what came before?**

The summary above does not paint a very comprehensive picture of the major health data standards maintained by the [HL7 Organization](http://www.hl7.org/about/index.cfm?ref=nav) before FHIR. 

If you're interested in a more thorough history lesson about the **HL7 V2, V3, and CDA** standards, check out these two slide decks and walk-throughs and send us any questions you might have!

https://pasteapp.com/p/Ggufyqh11of/s/5m7aiy75
https://pasteapp.com/p/If8ttW55K0J/s/4q19rk20
https://github.com/bhi-spring-591-2019/instructors/blob/master/HL7%20and%20XDSToolkit%20walkthrough.md

**Main Takeaway:** Previous HL7 standards are still in use today to varying degrees, but FHIR has recently experienced very fast growth and adoption.

https://www.healthit.gov/buzz-blog/interoperability/heat-wave-the-u-s-is-poised-to-catch-fhir-in-2019

**What about the `web standards` part of the summary?**

To understand FHIR better, we'll dive into what the aformentioned `latest web standards` are, how they facilitate `implementability`, and what this `implementability` could mean.

The key point to remember is: FHIR is a [RESTful API](https://medium.com/extend/what-is-rest-a-simple-explanation-for-beginners-part-1-introduction-b4a072f8740f), which puts it in a class of web standards that is very widely used in the tech field to transfer all kinds of data between different applications and systems. 

Some examples you might be familiar with: the [Twitter Search API](https://developer.twitter.com/en/docs/tweets/search/quick-start/premium-30-day), the [Github API](https://developer.github.com/v3/), [IBM's Watson Assistant](https://developer.ibm.com/patterns/watson-conversation-with-ibm-linuxone-systems/) and countless other services provide access to their data through a RESTful API.

*(Slack also has a REST API that you can easily play with - I started doing an analysis of the OpenMRS #fhir channel here if you're interested: https://github.com/pmanko/slack_analysis/blob/master/fhir_channel.ipynb)*

**Ok, FHIR is a RESTful API...** But what exactly does that mean?

We'll look into the **RESTful** part later, but lets first focus on **API**s (or **A**pplication **P**rogramming **I**nterfaces) in general.

Here's a diagram from https://learn.g2.com/api that illustrates the concept "in simple terms":

![https://learn.g2.com/hs-fs/hubfs/what-is-an-API-waiter-example.png?width=1200&name=what-is-an-API-waiter-example.png](https://learn.g2.com/hs-fs/hubfs/what-is-an-API-waiter-example.png?width=1200&name=what-is-an-API-waiter-example.png)

Say you have some app or service - in this case, a kitchen full of chefs that can create and output many exciting dishes. You also have a set of clients - in this case, the hungry customers - who  want to get at the provided services. 

However, these clients might be completely ignorant of how the "kitchen" works, what food it provides, and all the other intricacies of running a restaurant. 

That's where the API/waiter comes in. The waiter acts as an interface for the customers to interact with the kitchen, by translating the needs of the clients into a language the kitchen can understand, and delivering the required services back to the hungry clients. 

Ideally, this API/Waiter provides the customers with an experiance they've come to expect from other such fine establishments, so even though the kitchen might work completely differently, the experience is not unfamiliar. 

So, in summary, an API provides a standardized, (ideally) well-documented, and convenient endpoint for clients to interface with some service. 

If you want to learn a bit more about APIs and how they relate to FHIR, check out [Pascal Brandt's](https://talk.openmrs.org/u/pascal/summary) quick API & FHIR tutorial: https://psbrandt.io/fhir/

**Ok, now what about the RESTful Part?**

RESTful APIs are a subclass of Web APIs that define a set of standard **[Operations](https://restful-api-design.readthedocs.io/en/latest/methods.html)** on digital representations of objects called **[Resources](https://restful-api-design.readthedocs.io/en/latest/resources.html)**. 

The [official FHIR page](http://hl7.org/fhir/summary.html#2.17) iillustrates how foundational these two concepts are for the FHIR standard. 

**Resources** are mentioned in the second paragraph of the summary:

> FHIR solutions are built from a set of modular components called **Resources**...[that can] easily be assembled into working systems that solve real world clinical and administrative problems...
> 
> *source: http://hl7.org/fhir/summary.html#2.17*

These resources are defined to represent the various different concepts important in healtcare scenarios, includingpatients, clinical encounters, medications, and so on.

You can browse them all on the following page:  
https://www.hl7.org/fhir/resourcelist.html

**Operations** are highlighted [here](http://hl7.org/fhir/operationslist.html), and introduced as follows: 

>The RESTful API defines a set of common interactions (read, update, search, etc.) performed on a repository of typed resources. For further information concerning how operations are defined and invoked, see Extended Operations on the RESTful API.
> 
> This is a full list of the operations defined by this specification:
>
> *source: http://hl7.org/fhir/operationslist.html*


TODO: Incorporate better into flow
**In summary,**
Here are a few slides that outline what FHIR is:
- https://pasteapp.com/p/If8ttW55K0J/s/9mm9e825
- https://pasteapp.com/p/If8ttW55K0J/s/EPMk15fruiV

And what FHIR is NOT:
- https://pasteapp.com/p/If8ttW55K0J/s/8gw43cz9

**Main Gist: FHIR can serve as the electronic language of for healthcare data**


--> Provides a General Framework for Healthcare Data and Standardized Methods to manipulate this data
--> Aims to cover ~80% of Healthcare situations (maybe comment on which "situations" apply
--> Provides a standard method for extension to cover the otehr 20%
  
-----

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

https://uw-fhir.github.io/FHIRupUW/

https://fire.ly/training/hl7-fhir-overview-course/?utm_source=fhir_training_mailing20190820&utm_medium=email

### Advanced FHIR Topics
https://pasteapp.com/p/If8ttW55K0J/s/dcbcl3wi

Get in touch with us!

## To-Do
- [ ] Finish rough post outline w/ placeholders where necessary 
- [x] Compare w/ ITECH presentation to identify any gaps
- [ ] Insert and check all out-links
- [ ] Compile a new slide-deck and insert slides into placeholders
- [ ] Do a quick run-through and fix issues (logical, spelling, links, tutorial, etc.)
- [ ] Publish Talk post by 8/20
- [ ] Post to Slack



-----------------
## Notes and Edits

- Quickly go over idea of resource, and of GET/PUT/POST/UPDATE



By modeling healthcare concepts as resources and providing? some standard functionality for using these resources, FHIR is essenitally a RESTful API in line with many such APIs out there

```
overview of APIs again, and a quick look at OpenMRS API
--> OpenMRS actually has an API (Is it restful?) --> quick overview of Restful Web Services
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
