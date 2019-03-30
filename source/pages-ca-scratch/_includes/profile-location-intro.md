<!--- Text entered into this file will appear at the top of the profiles page before the Formal Views of the profile content. -->

This profile was generated from [HL7 StructureDefinition](https://www.hl7.org/fhir/organization.profile.json) on 2019-03-28 and constrained (not adapted directly from US Core).

**Notes:**
- PrescribeIT doesn't include Location resource - although it appears similar to ServiceDeliveryLocation in CDN v3 specs, eRx Service location is a profile on Organization not Location.
- Location is not profiled in OLIS or DHDR FIR specs.
- Location is profiled in ON PPR FHIR spec.
- Location.extension: ON PPR uses extensions to capture:
    - Location-Language (vs language of resource): Optional [Binding](http://ehealthontario.ca/fhir/ValueSet/ppr-HumanLanguage)
    - Location-Affiliation (vs managingOrganization: Optional - includes date range and affiliation type ... use of "with" needs further investigation)
    - LHIN code << Ontario specific requirement
- Location.identifier:
    - ON PPR: same / similar structure as Organization
- Location.status:
    - ON PPR: Optional,
      - Bound to [OperationalStatus](https://simplifier.net/ProvincialProviderRe/ppr-OrganizationOperationalStatus)
      - Extensions for:
        - Status Reason
        - Stauts Date
    - V3: Required, Bound to [ServiceDeliveryRoleStatus](https://infocentral.infoway-inforoute.ca/extra/ca/mr0206-html/html/vocabulary.html?type=vs&id=ServiceDeliveryRoleStatus)
    - Note: value sets above are different from eachother and (http://build.fhir.org/codesystem-location-status.html) ... v3 may be semantically equiv "terminated" vs "inactive"
- Location.name: Required in HL7v3 and PPR
- Location.alias: NOTE slicing on ON PPR FHIR profile to distinguish legal name, short name, other name (extension on other name for language codes)
- Location.type: Required in HL7v3 and PPR
    - not required in US Core R4
    - Bindings used by FHIR, CDN HL7v3 and PPR appear to all be different (**TODO - look deeper**)
    - ON Specific Requirement --- PPR uses slicing for OC (Org Class), OC (Org Subclass), OT (Org Type) where OC is mandatory BUT structure and bindings are the same for each (ignore)
- Location.telecom: mustSupport but not required in US Core, not required in CDN v3 or ON PCR
- Location.address: mustSupport but not required in US Core, required in CDN v3 or ON PCR (left not required)


{% include link-list.md %}
