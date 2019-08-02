<!--- Text entered into this file will appear at the top of the profiles page before the Formal Views of the profile content. -->

This profile was generated from [HL7 StructureDefinition](https://www.hl7.org/fhir/patient.profile.json) on 2019-03-28 and constrained during a review of US Core against Canadian sources.

Key differences from [USCoreR4 Patient](https://build.fhir.org/ig/HL7/US-Core-R4/StructureDefinition-us-core-patient.html):

- Removed US Race and Ethnicity (no Canadian requirement)
- Added Slice and example for Canadian Jurisdictional Health Number (JHN) with extension for version code
- Retained FHIR default ValueSet instead of US Simple-Language (some existing Canadian specs appear to use full http://tools.ietf.org/html/bcp47)

**Note:** Jurisdictional Health Number (JHN) - Version Code Extension

The Version Code is current captured separately from the JHN because, in Ontario at least, the JHN is a stable identifier whereas the version code changes over time.  

- The working assumption is that it is useful to have this stable identifier but not all of the Ontario specs reviewed stored it as a separate field.  In one case, it appears to be an Patient.identifier.coding.value instead of the identifier ...
- Example JHN and Patient Information from [Ontario Health Care Validation Reference Manual](http://www.health.gov.on.ca/english/providers/pub/ohip/ohipvalid_manual/ohipvalid_manual.pdf)
- Question: would specific examples like this be helpful to illustrate Canadian requirements?

**Note** Data Absent Reason
In situations where information on a particular data element is missing and the Responder knows the precise reason for the absence of data, Responders SHALL send the reason for the missing information using values (such as nullFlavors) from the value set where they exist or using the dataAbsentReason extension (http://hl7.org/fhir/StructureDefinition/data-absent-reason).
