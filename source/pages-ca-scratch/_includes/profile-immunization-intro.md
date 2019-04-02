<!--- Text entered into this file will appear at the top of the profiles page before the Formal Views of the profile content. -->

This profile was generated from [HL7 StructureDefinition](https://www.hl7.org/fhir/immunization.profile.json) on 2019-03-28 and constrained during a review of US Core against Canadian sources.

**Note** The USCoreR4 resource supports recording of vaccines not given (refused) with reasons.  The [Ontario Immunization Connect (ICON) profiles](https://simplifier.net/digitalhealthimmuniz/~resources?category=Profile&sortBy=RankScore_desc) has fixed values for Immunization.status and Immunization.notGiven that restrict use to completed vaccinations. **<< As in USCoreR4, refused vaccines are supported in this profile.**

Key differences from [USCoreR4 Immunization](https://build.fhir.org/ig/HL7/US-Core-R4/StructureDefinition-us-core-immunization.html):
- Immunization.code bound to ValueSet with Canadian vaccine codes
- Immunization.patient reference changed to profile-patient
- Immunization.occurrence[x] restricted to DateTime, optional **ext_estimated** extension added to identify estimated dates to be more consistent with ICON and CDN HL7v3 specs
- included other Immunization resource elements used in the ICON spec for visibility


**[ToDo]:**

[X] review USCoreR4 profile and draft extensions and restrictions

[X] review structure against pan-CDN HL7 v3
- scanned only

[x] review structure against existing CAD FHIR specs
- Note that [ICON](https://simplifier.net/digitalhealthimmuniz/~resources?category=Profile&sortBy=RankScore_desc) has a number of different profiles, review was not exhaustive
  - Immunization.statusReason is not here assuming intent is the same as Immunization.explanation.reason in ICON spec

[x] review and update terminology bindings
- needs review / refinement

[] add constraints (cross element) from USCoreR4

[] refine constraints (cross element) to CAD requirements ?

[] ?

{% include link-list.md %}
