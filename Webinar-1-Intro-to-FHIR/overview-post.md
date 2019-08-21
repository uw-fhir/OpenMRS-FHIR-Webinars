
*Check out the [Webinars Github Page](https://github.com/uw-fhir/OpenMRS-FHIR-Webinars/tree/master/Webinar-1-Intro-to-FHIR) for another view of this tutorial*\
*Check out https://pasteapp.com/p/OzVTNeWZln3/s/hljtep4x for the companion slide deck*

# An Introduction to the FHIR API

## Outline
- [An Introduction to the FHIR API](#an-introduction-to-the-fhir-api)
  - [Outline](#outline)
  - [Learning Objectives](#learning-objectives)
  - [So, what is FHIR?](#so-what-is-fhir)
  - [Related Projects and Technologies](#related-projects-and-technologies)
  - [Spec vs. Implementation](#spec-vs-implementation)
  - [FHIR API Tutorial](#fhir-api-tutorial)
  - [Explore on your own!](#explore-on-your-own)
    - [Advanced FHIR Topics](#advanced-fhir-topics)
  - [To-Do](#to-do)
  - [Notes and Edits](#notes-and-edits)

---

## Learning Objectives

1. Recognize the basic features and uses of modern **web APIs** & how **FHIR fits** in as a RESTful API.

2. Have a general **understanding** of the FHIR standard for health care data exchange, including an overview of the **history**, **purpose**, **scope**, the **adoption** and **implementation** situation.
    * Identify gaps between the spec and its implementations
    * Understand what functionality & features are **NOT** part of FHIR

3. Have a general **awareness** of major **projects**, **collaborations**, **implementations**, and **technologies** that use or focus on FHIR.

4. Work through a FHIR tutorial that **queries** data from a **FHIR endpoint** to implement a simple cardiovascular risk calculator.

5. Be able to explore FHIR independently through provided access to **projects**, **readings**, **tutorials**, and other useful resources

6. Participate in an **ideation session** on opportunities for **FHIR** in the **OpenMRS** community

---

## So, what is FHIR?

**FHIR** stands for **Fast** **Healthcare** **Interoperability** **Resources**.

According to the [summary in the official documentation](http://hl7.org/fhir/summary.html#2.17), FHIR is a
> "...next generation standards framework created by HL7. FHIR combines the best features of HL7's v2 , HL7 v3  and CDA  product lines while leveraging the **latest web standards** and applying a tight focus on **implementability**."
> 
>*source: http://hl7.org/fhir/summary.html#2.17*

**If FHIR is "next generation", what came before?**

The summary above does not paint a very comprehensive picture of the major health data standards maintained by the [HL7 Organization](http://www.hl7.org/about/index.cfm?ref=nav) before FHIR. 

If you're interested in a more thorough history lesson about the **HL7 V2, V3, and CDA** standards, check out this slide deck and an associated [walk-through](https://github.com/bhi-spring-591-2019/instructors/blob/master/HL7%20and%20XDSToolkit%20walkthrough.mds) and send us any questions you might have!

<iframe src="https://pasteapp.com/p/OzVTNeWZln3/s/4q19rk20/embed" width="1200" height="800" scrolling="no" frameborder="0" allowfullscreen></iframe>

Walk-through: 

**Main Takeaway for Now:** Previous HL7 standards are still in use today to varying degrees, but FHIR is experienced very fast growth, maturation, and adoption.

Here's a slightly-outdated map supporting that point - at least in the United States:
![FHIR-USA-Map](https://www.healthit.gov/buzz-blog/wp-content/uploads/2018/10/fhir-hospital-hrr-blog.png)

And here's some more on the topic: https://www.healthit.gov/buzz-blog/interoperability/heat-wave-the-u-s-is-poised-to-catch-fhir-in-2019

---

**What about the `web standards` part of the summary?**

To understand FHIR better, we'll dive into what the aformentioned `latest web standards` are, how they facilitate `implementability`, and what this `implementability` could mean.

The key point to remember is: FHIR is a [RESTful API](https://medium.com/extend/what-is-rest-a-simple-explanation-for-beginners-part-1-introduction-b4a072f8740f), which puts it in a class of web standards that is very widely used in the tech field to transfer all kinds of data between different applications and systems. 

Some examples you might be familiar with: the [Twitter Search API](https://developer.twitter.com/en/docs/tweets/search/quick-start/premium-30-day), the [Github API](https://developer.github.com/v3/), [IBM's Watson Assistant](https://developer.ibm.com/patterns/watson-conversation-with-ibm-linuxone-systems/) and countless other services provide access to their data through a RESTful API.

*Note: Slack also has a REST API that you can easily play with - I started doing an analysis of the OpenMRS #fhir channel here if you're interested: https://github.com/pmanko/slack_analysis/blob/master/fhir_channel.ipynb)*

----

**Ok, FHIR is a RESTful API...** But what exactly does that mean?

First, let's focus on what **API**s (or **A**pplication **P**rogramming **I**nterfaces) are in general.

Here's a diagram from https://learn.g2.com/api that illustrates the concept "in simple terms":

![https://learn.g2.com/hs-fs/hubfs/what-is-an-API-waiter-example.png?width=1200&name=what-is-an-API-waiter-example.png](https://learn.g2.com/hs-fs/hubfs/what-is-an-API-waiter-example.png?width=1200&name=what-is-an-API-waiter-example.png)

Say you have some app or `service` - in this case, a kitchen full of chefs that can create and output many exciting dishes. You also have a set of `clients` - very hungry restaurant patrons - who  want to get at the provided services.

However, these `clients` might be completely ignorant of how this specific kitchen (`service`) operates, what food is provided, how this food is made and dispensed, and all the other intricacies of running a restaurant. Yet these `clients` still want access to this and other such restaurant `services` with minimal hassle.

That's where the waiter (`API`) comes in. The waiter acts as an interface that the customers to interact with, and translates their needs to the kitchen in a way the kitchen can understand. Finally, the waiter/`API` devlivers the services to the `clients`, isolating the kitchen from individual interactions. 

Ideally, the waiter/`API` provides the customers with an experiance they've come to expect from other such fine establishments. Even if this kitchen/`service` operates completely differently and - maybe a different cuisine, done on a different scale, at a different pricepoint - the experience as viewed by the `clients` using the waiter/`API` is not unfamiliar.

**In summary,** an ideal `API` provides a standardized, well-documented, and convenient endpoint for `clients` to interface with a given `app` or `service`. 

If you want to learn a bit more about APIs and how they relate to FHIR, check out [Pascal Brandt's](https://talk.openmrs.org/u/pascal/summary) quick API & FHIR tutorial: https://psbrandt.io/fhir/

---

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

---

**Let's step back a bit** and talk about what exactly is part of the FHIR standard, and what falls out of scope - or is addressed by a related project or technology.

- https://pasteapp.com/p/If8ttW55K0J/s/9mm9e825
- https://pasteapp.com/p/If8ttW55K0J/s/EPMk15fruiV

And what FHIR is NOT:
- https://pasteapp.com/p/If8ttW55K0J/s/8gw43cz9

**FHIR provides a framework for the representation of healthcare data and methods for sending and retrieving this data**

It has the potential to be the language that all kinds of different healthcare apps and services - 
EHRs, personal health apps, fitness trackers, Apple Health, patient portals, clinical labs, and so on - communicate with.

FHIR also aims to cover ~80% of Healthcare `situations`, and provides a [standard method for extension](https://www.hl7.org/fhir/extensibility.html) to cover the other 20%.
  
----

## Related Projects and Technologies
<iframe src="https://pasteapp.com/p/OzVTNeWZln3/s/HQu2XIzmDF3/embed" width="1200" height="800" scrolling="no" frameborder="0" allowfullscreen></iframe>

**FHIR Tutorials**
* https://psbrandt.io/fhir/
* https://github.com/uw-fhir/fhir-api-tutorial

**SMART on FHIR**
* https://docs.smarthealthit.org/
* https://gallery.smarthealthit.org/ 

tutorial: https://github.com/uw-fhir/smart-on-fhir-tutorial

**CDS Hooks**
* https://cds-hooks.org/
* https://sandbox.cds-hooks.org/

UW FHIR tutorial: https://github.com/uw-fhir/CDS-Hooks-Tutorial
Cerner tutorial: https://github.com/cerner/cds-services-tutorial

**Apple Health Records**
* https://www.apple.com/healthcare/health-records/

**Google Cloud Healthcare API and FHIR**
* https://cloud.google.com/healthcare/docs/concepts/fhir
SoF + App Galleries

**AWS and FHIR**
* https://aws.amazon.com/blogs/publicsector/achieving-healthcare-interoperability/
CDS Hooks

## Spec vs. Implementation

There's a large difference between the FHIR specifications and the actual implementation of a standard.


FHIR is relatively mature as an API, and the documented features are relatively comprehensive

The HAPI


## FHIR API Tutorial
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


        Ideation:

        What FHIR might enable in each participant’s work on OpenMRS


        What barriers / issues / gaps might pop up
 
 
        Open Floor : other questions / ideas / comments

Thoughts, comments:

use talk for continued discussion
