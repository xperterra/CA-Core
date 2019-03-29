---
title: Implementation Guide HomePage
layout: default
---

{:.no_toc}

<!-- TOC  the css styling for this is \pages\assets\css\project.css under 'markdown-toc'-->

* Do not remove this line (it will not be displayed)
{:toc}


<!-- end TOC -->

### Introduction

This 'implementation guide' is a **living document** containing notes and draft profiles developed captured while reviewing the [USCoreR4 Implementation Guide](http://build.fhir.org/ig/HL7/US-Core-R4/) against various Canadian sources, including:
- [PrescribeIT implementation guides](https://specs.prescribeit.ca/R2.0/)
- [ON Implementation guides](https://ehealthontario.on.ca/en/architecture/standards/draft), including:
  - [PCR](https://simplifier.net/provincialclientregi)
  - [PPR](https://simplifier.net/provincialproviderre)
  - [DHDR](https://simplifier.net/ontariodigitalhealth)
  - [OLIS](https://simplifier.net/ontariolaboratoriesi)
  - [Immunization](https://simplifier.net/digitalhealthimmuniz)
- [Australian baseline](http://fhir.hl7.org.au/fhir/base2017Jul/)
- [pan-Canadian HL7v3 specs](https://infocentral.infoway-inforoute.ca/extra/ca/mr0206-html/html/start.html)


### Draft Profiles

The following profiles have been developed over the course of the review process described above.  The objective is to refine these to a point where they can be used as a baseline set of Canadian FHIR profiles similar to the USCore.

{% include list-simple-profiles.xhtml %}



A [General Guidance Section](general-guidance.html) will likely be developed to support use of the profiles.  The page currently contains placeholder content from USCoreR4.  This content may be a useful basis for some Canadian content later.


###  Conformance Requirements

A [Capability Statements Section](capstatements.html) will likely also be developed to outline Canadian conformance requirements for clients and servers. The page currently contains placeholder content from USCoreR4.  This content may be a useful basis for some Canadian content later.

----

Authors: TBD

{% include link-list.md %}
