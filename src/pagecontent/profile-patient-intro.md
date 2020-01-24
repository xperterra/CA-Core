<!--- Text entered into this file will appear at the top of the profiles page before the Formal Views of the profile content. -->
# CA Core Patient Profile
This Patient profile sets minimum expectations for the Patient resource to record, search and fetch demographics and other administrative information about an individual receiving care or other health-related services.

Since not all concepts are included within the base FHIR Patient resource, this profile defines core localisation concepts for use in an Canadian context.

## Differences from US Core
**Note:** This profile was generated from [HL7 StructureDefinition](https://www.hl7.org/fhir/patient.profile.json) on 2020-01-07 and constrained during a review of US Core against Canadian sources.

Key differences from [USCoreR4 Patient](https://build.fhir.org/ig/HL7/US-Core-R4/StructureDefinition-us-core-patient.html):

* Removed US Race (no Canadian requirement)
* Added slice and extensions to Patient.identifier
* Added extensions to Patient.address
* Retained FHIR default ValueSet instead of US Simple-Language (some existing Canadian specs appear to use full http://tools.ietf.org/html/bcp47)

## Mandatory Data Elements
All elements or attributes defined in FHIR have cardinality as part of their definition - a minimum number of required appearances and a maximum number.

Most elements in FHIR specification have a minimum cardinality of 0, which means that they may be missing from a resource when it is exchanged between systems. 

In this Canadian Core Patient Profile all elements are optional, i.e., there is no element with a minimum cardinality of 1. However, some optional elements (e.g., identifier) have required components that MUST be present if that optional element is provided.

### Data Absent Reason
In situations where the minimum cardinality of an element or attribute is 1 and information is missing and the Responder knows the precise reason for the absence of data, Responders SHALL send the reason for the missing information using values (such as [NullFlavor](https://www.hl7.org/fhir/extension-iso21090-nullflavor.html)) from the value set where they exist or using the [DataAbsentReason](http://hl7.org/fhir/StructureDefinition/data-absent-reason) extension.

## Must Support Data Elements
Some elements are labeled as MustSupport meaning that implementations that produce or consume resources SHALL provide "support" for the element in some meaningful way (see [Must Support](https://build.fhir.org/ig/scratch-fhir-profiles/CA-Core/general-guidance.html#must-support) definition).

Following elements are marked as Must Support in the Canadian Patient profile to aid record matching in databases with many pediatric records.

**Must Support elements:**
1. an identifier
2. a patient name
3. contact detail (e.g. a telephone number or an email address)
4. a birth date

## Usage Note
TBD
