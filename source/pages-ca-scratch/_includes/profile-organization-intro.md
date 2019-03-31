<!--- Text entered into this file will appear at the top of the profiles page before the Formal Views of the profile content. -->

This profile was generated from [HL7 StructureDefinition](https://www.hl7.org/fhir/organization.profile.json) on 2019-03-28 and constrained during a review of US Core against Canadian sources.

Key differences between this profile and [USCoreR4 Organization](https://build.fhir.org/ig/HL7/US-Core-R4/StructureDefinition-us-core-organization.html) are:
- Added extension for Communication language to be consistent with Location (ON PPR has a Location Language element, added ext_communication to support requirement more generally)
- Added extension for Affiliation to be consistent with Location (PPR has an Affiliation extension that appears to have a different semantic meaning than Organization.partOf)
- Added slicing for Canadian Jurisdictional Provider identifiers, licensing (same structure as Practitioner, Location)
- Organization.active: Required in US Core but not in CDN specs reviewed, **removed constraint**

- Notes: Canadian spect have variation in use of many remaining elements including endpoint.

**[ToDo]:**
[x] review structure against USCoreR4 profile and draft constraints

[x] review structure against pan-CDN HL7 v3

[x] review structure against existing CAD FHIR specs

[x] review and update terminology bindings

[] add additional constraints (cross element) from USCoreR4

[] refine constraints (cross element) to CAD requirements ?

[] ?

{% include link-list.md %}
