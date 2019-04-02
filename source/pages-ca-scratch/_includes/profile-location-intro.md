<!--- Text entered into this file will appear at the top of the profiles page before the Formal Views of the profile content. -->

This profile was generated from [HL7 StructureDefinition](https://www.hl7.org/fhir/location.profile.json) on 2019-03-28 and constrained during a review of US Core against Canadian sources.

Key differences from [USCoreR4 Location](https://build.fhir.org/ig/HL7/US-Core-R4/StructureDefinition-us-core-location.html):
- Added extension for Communication language to be consistent (ON PPR has a Location Language element, added ext_communication to support requirement more generally)
- Added extension for Affiliation (ON PPR has an Affiliation extension that appears to have a different semantic meaning than Location.managingOrganization)  
- Added slicing for Canadian Jurisdictional Provider identifiers, licensing (same structure as Practitioner, Organization)

**[ToDo]:**

[x] review USCoreR4 profile and draft extensions and restrictions

[x] review structure against pan-CDN HL7 v3

[x] review structure against existing CAD FHIR specs

[x] review and update terminology bindings

[] PRN, LN identifier.system: **should the list of URIs be constrained using valueSets?**

[] add constraints (cross element) from USCoreR4

[] refine constraints (cross element) to CAD requirements ?

[] ?

{% include link-list.md %}
