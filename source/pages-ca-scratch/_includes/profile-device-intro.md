<!--- Text entered into this file will appear at the top of the profiles page before the Formal Views of the profile content. -->

This profile was generated from [HL7 StructureDefinition](https://www.hl7.org/fhir/device.profile.json) on 2019-03-28 and constrained during a review of US Core against Canadian sources.

**Note:**
- USCoreR4 appears to use both
  - a Universal Device Identifier (barcode) provided by one of multiple entities (e.g. [GS1 GDSN](https://www.gs1.org/standards/gdsn))
  - Device Types from SNOMED CT
- Canadian work appears to use both:
  - codes from Canadian regulators (e.g. [Health Canada Device NTP](https://tgateway.infoway-inforoute.ca/hc.html?id=2.16.840.1.113883.2.20.6.1.DeviceNTP) or [OPINIONS](http://www.atlanticpharmaceutical.ca)
  - Device Types from SNOMED CT
- [GS1 Canada is active in the Medical Device space](https://www.gs1ca.org/CHPR2011/) whereas Infoway's Device NTP valueSet shows only a couple sample codes **<< what direction is this headed in?**

Key differences from [USCoreR4 Device](https://build.fhir.org/ig/HL7/US-Core-R4/StructureDefinition-us-core-device.html):
- included more udiCarrier elements for visibility
- changed reference to profile-patient

**[ToDo]:**

[x] review USCoreR4 profile and draft extensions and restrictions

[x] review structure against pan-CDN HL7 v3
- [HL7v3 ManufacturedClinicalDevice](https://infocentral.infoway-inforoute.ca/extra/ca/mr0206-html/html/message.html?COCT_MT141007CA)

[x] review structure against existing CAD FHIR specs
- No Canadian profiles on FHIR Device resource were identified on quick review of the [Canadian FHIR Registry](https://simplifier.net/organization/canadianfhirregistry)

[x] review and update terminology bindings
- USCoreR4 Device.type is bound to valueSet [device-kind](http://build.fhir.org/valueset-device-kind.html)
- base FHIR resource is bound to [device-type](http://build.fhir.org/valueset-device-type.html)
- the valueSets appear to be identical but the former is used less frequently (only on Device)
- used the binding in USCoreR4.

[] add constraints (cross element) from USCoreR4

[] refine constraints (cross element) to CAD requirements ?

[] ?

{% include link-list.md %}
