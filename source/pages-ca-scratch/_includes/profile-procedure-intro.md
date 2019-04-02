<!--- Text entered into this file will appear at the top of the profiles page before the Formal Views of the profile content. -->

This profile was generated from [HL7 StructureDefinition](https://www.hl7.org/fhir/procedure.profile.json) on 2019-03-28 and constrained during a review of US Core against Canadian sources.

Key differences from [USCoreR4 Procedure](https://build.fhir.org/ig/HL7/US-Core-R4/StructureDefinition-us-core-procedure.html):
- subject reference changed to profile-patient

**[ToDo]:**

[x] review USCoreR4 profile and draft extensions and restrictions

[] review structure against pan-CDN HL7 v3

[] review structure against existing CAD FHIR specs

[] review and update terminology bindings
- Procedure.code binding from USCoreR4 not carried forward due to inclusion of AMA CPT coding not typically used in Canada
- http://hl7.org/fhir/ValueSet/procedure-code valueset has been retained although it is broader than the list of [Professional Service Codes](https://infocentral.infoway-inforoute.ca/extra/ca/mr0206-html/html/vocabulary.html?type=vs&id=ActProfessionalServiceCode) which appears to be used in the Canadian HL7v3 specs.

[] add constraints (cross element) from USCoreR4

[] refine constraints (cross element) to CAD requirements ?

[] ?

{% include link-list.md %}
