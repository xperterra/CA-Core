<!--- Text entered into this file will appear at the bottome of the profiles page after the Formal Views of the profile content. -->
## Identifiers
Mutiple individual healthcare identifiers may be provded in Patient.identifier element. 

However, to support particular types federal patient and person health numbers used by all jurisdictions across Canada following optional types were defined to uniquely identifying patients:
* Canadian Passport Number
* Jurisdictional Person Identification
* Jurisdictional Health Number

### Canadian Passport Number (PPN)
A unique number assigned to the document affirming that a person is a citizen of Canada. 

URI to use with this identifier type: https://fhir.infoway-inforoute.ca/NamingSystem/ca-passport-number

**Example:**
```
{
  "type": {
    "coding": [
      {
        "system": "http://terminology.hl7.org/CodeSystem/v2-0203",
        "code": "PPN"
      }
    ]
  },
  "system": "https://fhir.infoway-inforoute.ca/NamingSystem/ca-passport-number",
  "value": "AB123456",
  "period": {
    "start": "2005-05-11",
    "end": "2015-05-11"
  }
}
```

### Jurisdictional Patient Identifier Number (JPID)
This patient identifier type identifies a number issued in Canada to administer various government programs. 

URIs used with this identifier type:
* Canada, Social Insurance Number (SIN) - https://fhir.infoway-inforoute.ca/NamingSystem/ca-social-insurance-number
* Canada Permanent Resident Card Number - https://fhir.infoway-inforoute.ca/NamingSystem/ca-permanent-resident-card-number
* Canada First Nation Indian registry number (band ID) - https://fhir.infoway-inforoute.ca/NamingSystem/ca-federal-firstnation-band-id
* Indigenous and Northern Affairs Canada health card number - https://fhir.infoway-inforoute.ca/NamingSystem/ca-indigenous-northern-affairs-number
* Interim Federal Health Program identifier - https://fhir.infoway-inforoute.ca/NamingSystem/ca-interim-federal-health-id

**Example:**
```
{
  "type": {
    "coding": [
      {
        "system": "http://terminology.hl7.org/CodeSystem/v2-0203",
        "code": "JPID"
      }
    ]
  },
  "system": "https://fhir.infoway-inforoute.ca/NamingSystem/ca-social-insurance-number",
  "value": "923456789"
  }
}
```

### Jurisdictional Health Number (JHN)
This patient identifier type identifies a number issued in Canada to get recognized for service and stay connected to related support programs.

URIs used with this identifier type:
* Canada Veteran's Affairs health card number - https://fhir.infoway-inforoute.ca/NamingSystem/ca-veterans-affairs-health-id 
* Canada Correctional Service health card number - https://fhir.infoway-inforoute.ca/NamingSystem/ca-correctional-service-health-id
* Canada Royal Canadian Mounted Police (RCMP) health card number - https://fhir.infoway-inforoute.ca/NamingSystem/ca-royal-mounted-police-health-id
* Canada Armed Forces health card number - https://fhir.infoway-inforoute.ca/NamingSystem/ca-armed-forces-health-id 

**Extension**
The [Version Code](http://hl7.org/fhir/ca/core/StructureDefinition/ext-identifierversion) extension is added to indicate the currency/validity of an identifier.

The rational is that the version code is current captured separately from the JHN because, in Ontario at least, the JHN is a stable identifier whereas the version code changes over time. 
- The working assumption is that it is useful to have this stable identifier but not all of the Ontario specs reviewed stored it as a separate field.  In one case, it appears to be an Patient.identifier.coding.value instead of the identifier ...
- Example JHN and Patient Information from [Ontario Health Care Validation Reference Manual](http://www.health.gov.on.ca/english/providers/pub/ohip/ohipvalid_manual/ohipvalid_manual.pdf)
- Question: would specific examples like this be helpful to illustrate Canadian requirements?

**Example:**
```
{
  "type": {
    "coding": [
      {
        "system": "http://terminology.hl7.org/CodeSystem/v2-0203",
        "code": "JHN"
      }
    ]
  },
  "system": "https://fhir.infoway-inforoute.ca/NamingSystem/ca-armed-forces-health-id",
  "value": "A98765439"
  }
}
```



## Patient Gender and Sex
Many systems and organizations only provide for a single attribute that aspires to represent all aspects of a patient's gender and sex with a single value. However, there are many considerations around sex and gender documentation and interoperability.

The [FHIR Specification](https://www.hl7.org/fhir/patient.html#gender) provides guidance and background for representing patient gender.

Canadian Patient profile defines following extensions:
* **Gender Identity** - an indication from the patient about what gender they consider themselves to be. 
* **Sex assigned at Birth** - the sex assigned at birth, as documented on the birth registration.
* **Preferred Pronoun** - an indication from the patient about what pronoun to use in correspondence.

**!! TO BE COMPLETED !!**

## Telecom
A Patient may have multiple ways to be contacted with different uses or applicable periods. This Patient profile allows multiple contact points (e.g. a telephone number or an email address) by which the individual may be contacted.

To indicate the preferred way to contact use Patient.telecom.rank attribute ([ContactPoint.rank](https://www.hl7.org/fhir/datatypes.html#contactpoint) component) that specifies a preferred order in which to use a set of contacts. ContactPoints with lower rank values are more preferred than those with higher rank values.

## Address
The Patient profile is provided for use in a Canadian context where some constraint on content is desirable to guarantee the quality of the Canadian address whilst still supporting other type of address (e.g., other countries or unstructured addresses).

### Canadian postal code
If an address in the Patient resource instance represents Canadian address, it SHOULD follow Canadian postal code format.

The Canadian Postal Code is a six-character uniformly structured and SHOULD be in uppercase alphanumeric code in the form "ANA NAN", where "A" represents an alphabetic character and "N" represents a numeric character, with one space between the first three and the last three characters. 

A hyphen SHOULD NOT be used (example of UNacceptable format: T0L-1K0).

### Preferred 
The [Preferred](http://hl7.org/fhir/StructureDefinition/iso21090-preferred) is the FHIR standard defined extension used in Patient.address is a flag denoting whether parent address item is preferred.

### No Fixed Address
The [No Fixed Address](http://hl7.org/fhir/ca/core/StructureDefinition/no-fixed-address) extension applies to the Patient.address to indicate that there is an assertion that there is no fixed address (e.g., homeless).

## Marital Status
The binding for this element is [extensible](https://www.hl7.org/fhir/terminologies.html#extensible) meaning that to be conformant, codes in this element SHALL be from the specified value set if any of the codes within the value set can apply to the concept being communicated.

Systems can send additional codes (Stats Canada, SNOMED CT, etc.) but can only do that if they also send the relevant HL7-assigned codes.

