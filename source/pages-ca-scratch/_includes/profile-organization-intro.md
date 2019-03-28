<!--- Text entered into this file will appear at the top of the profiles page before the Formal Views of the profile content. -->

This profile was generated from [HL7 StructureDefinition](https://www.hl7.org/fhir/organization.profile.json) on 2019-03-28 and constrained (not adapted from US Core).

**Notes:**
- Organization.identifier: Slicing carried over from Practitioner Profile
- Organization.active: Required in US Core but not in CDN specs reviewed, removed constraint
- Organization.type: Required CDN HL7 v3 but not required in any of the FHIR profiles reviewed.
- Organization.name: Required in US Core, CDN HL7 v3, etc
- Organization.alias: NOTE slicing on ON PPR FHIR profile to distinguish legal name, short name, other name (extension on other name for language codes)
- Organization.telecom: Required in US Core, CDN HL7 v3 but not all FHIR profiles reviewed
- Organization.address: Required in US core but not in all CDN specs reviewed.

Lots of variation in use of the remaining elements including endpoint.

{% include link-list.md %}
