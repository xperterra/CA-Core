<!--- Text entered into this file will appear at the top of the profiles page before the Formal Views of the profile content. -->

This profile was generated from [HL7 StructureDefinition](https://www.hl7.org/fhir/condition.profile.json) on 2019-03-28 and constrained during a review of US Core against Canadian sources.

Key differences from [USCoreR4 Condition](https://build.fhir.org/ig/HL7/US-Core-R4/StructureDefinition-us-core-condition.html):
- Condition.category bound to HL7 default [Condition Category Codes](file:///Users/russ/github/CA-Scratch/output/StructureDefinition-profile-observation.html)
- Condition.codes bound to [Canadian Health Concern Code](https://tgateway.infoway-inforoute.ca/singlesubset.html?id=2.16.840.1.113883.2.20.3.278&versionid=20181031) instead of [US Core Problem Value Set](http://hl7.org/fhir/us/core/ValueSet/us-core-problem)

**[ToDo]:**

[x] review USCoreR4 profile and draft extensions and restrictions

[x] review structure against pan-CDN HL7 v3

[x] review structure against existing CAD FHIR specs

[x] review and update terminology bindings
- [US Core Condition Category Codes](https://build.fhir.org/ig/HL7/US-Core-R4/ValueSet-us-core-condition-category.html) extends the default list used here with additional value health-concern **<< is this needed?**
- The [HL7 ConditionCode ValueSet](http://hl7.org/fhir/ValueSet/condition-code) on the base FHIR Condition resource appears to provide a shorter list of common Dx **<< which is preferable?**

[] add constraints (cross element) from USCoreR4

[] refine constraints (cross element) to CAD requirements ?

[] ?

{% include link-list.md %}
