---
title: General Guidance
layout: default
active: terminology
---

**===========


This page currently contains placeholder content from USCoreR4.  This content may be a useful basis for some Canadian content later.


===========**


This section outlines important definitions and interpretations and requirements common to all  actors used in this guide.
The conformance verbs used are defined in [FHIR Conformance Rules].

---

<!-- TOC  the css styling for this is \pages\assets\css\project.css under 'markdown-toc'-->
**Contents**

* Do not remove this line (it will not be displayed)
{:toc}

---

<!-- end TOC -->

### General Guideance

TBD

### Must Support
In the context of , *Must Support* on any data element SHALL be interpreted as follows:


*  Responders SHALL be capable of including the data element as part of the query results as specified by the [ Server Capability Statement].
*  Requestors SHALL be capable of processing resource instances containing the data elements without generating an error or causing the application to fail. In other words  Requestors SHOULD be capable of displaying the data elements for human use or storing it for other purposes.
* In situations where information on a particular data element is not present and the reason for absence is unknown,  Responders SHALL NOT include the data elements in the resource instance returned as part of the query results.
* When querying  Responders,  Requestors SHALL interpret missing data elements within resource instances as data not present in the  Responder's systems.
* In situations where information on a particular data element is missing and the  Responder knows the precise reason for the absence of data,  Responders SHALL send the reason for the missing information using values (such as nullFlavors) from the value set where they exist or using the dataAbsentReason extension.
*  Requestors SHALL be able to process resource instances containing data elements asserting missing information.


* NOTE: Typically * Responder* Actor = Server and * Requestor Actor* = Client
* NOTE:  Responders who do not have the capability to store or return a data element tagged as Supported in  profiles can still claim conformance to the  profiles per the  conformance resources.
* NOTE: The above definition of Supported is derived from HL7v2 concept "Required but may be empty - RE" described in HL7v2 V28_CH02B_Conformance.doc.
* NOTE: Readers are advised to understand [FHIR Terminology] requirements, [FHIR RESTful API] based on the HTTP protocol, along with [FHIR Data Types], [FHIR Search] and [FHIR Resource] formats before implementing  requirements.

### Referencing  profiles

Profiles in this guide [reference]({{site.data.fhir.path}}references.html) other FHIR resources that are also profiles.  This is defined in the formal profile definitions.  For any other references not formally defined in a profiles, the referenced resource SHOULD be a profile if a profile exists for the resource type.  ***add examples***

### Using Codes in  profiles

#### Extensible binding for CodeableConcept Datatype
{:.no_toc}

Extensible binding to a value set definition for this IG means that if the data type is CodeableConcept, then one of the coding values SHALL be from the specified value set if a code applies, but if no suitable code exists in the value set and no further restrictions have been applied (such as the max valueset binding described in the next section), alternate code(s) may be provided in its place. If only text available, then just text may be used.

#### Extensible + Max-ValueSet binding for CodeableConcept Datatype
{:.no_toc}

For this IG, we have defined the Extensible + Max-ValueSet binding to allow for either a code from the defined value set or text if the code is not available.  (for example, legacy data). This means, unlike a FHIR extensible binding, alternate code(s) are not permitted and a text value SHALL be supplied if the code is not available.  However, multiple codings (translations) are allowed as is discussed below.

Example: Immunization resource vaccineCode's CVX coding - the source only has the text "4-way Influenza" and no CVX code.

    \{
      "resourceType": "Immunization",
      ...
      "vaccineCode": {
        "text":"4-way Influenza"
      },
      ...
    }


#### Required binding for Code Datatype
{:.no_toc}

Required binding to a value set definition for this IG means that one of the codes from the specified value set SHALL be used. If only text is available or the local (proprietary, system) code cannot be mapped to one of the required codes the [core specification] provides guidance which we have summarized:

1.  Send the resource with the code element empty
2.  Use the [DataAbsentReason Extension] in the data type
3.  Use the code ‘unsupported’ - The source system wasn't capable of supporting this element.

Note that when a query uses a status parameter, a status will be ambiguous.

Example: AllergyIntolerance resource with a status that is text only or cannot be mapped to the status value set.

     \{
       "resourceType”:“AllergyIntolerance”,
       ...
       “\_status”:{
        “url” : “{{site.data.fhir.path}}StructureDefinition/data-absent-reason”,
       “valueCode” : “unsupported”
        ...
      },
     }

#### Required binding for CodeableConcept Datatype
{:.no_toc}

Required binding to a value set definition means that one of the codes from the specified value set SHALL be used and using only text is not valid. In this IG, we have defined the Extensible + Max-ValueSet binding to allow for either a code from the specified value set or text. Multiple codings (translations) are permitted as is discussed below.


#### Using multiple codes with CodeableConcept Datatype
{:.no_toc}

Alternate codes may be provided in addition to the standard codes defined in required or extensible value sets. The alternate codes are called “translations”. These translations may be equivalent to or narrower in meaning to the standard concept code.

Example of multiple translation for Body Weight concept code.


    "code": {
        "coding": [
         {
            "system": "http://loinc.org",  //NOTE:this is the standard concept defined in the value set//
            "code": "29463-7",
            "display": "Body Weight"
          },
    //NOTE:this is a translation to a more specific concept
         {
            "system": "http://loinc.org",
            "code": "3141-9",
            "display": "Body Weight Measured"
          },
    //NOTE:this is a translation to a different code system (Snomed CT)
         {
            "system": "http://snomed.info/sct",
            "code":  “364589006”,
            "display": "Body Weight"
          }
    //NOTE:this is a translation to a locally defined code
         {
            "system": "http://AcmeHealthCare.org",
            "code":  “BWT”,
            "display": "Body Weight"
          }
        ],
        "text": "weight"
      },

Example of translation of CVX vaccine code to NDC code.


    "vaccineCode" : {
        "coding" : [
          {
            "system" : "{{site.data.fhir.path}}sid/cvx",
            "code" : "158",
            "display" : "influenza, injectable, quadrivalent"
          },
          {
            "system" : "{{site.data.fhir.path}}sid/ndc",
            "code" : "49281-0623-78",
            "display" : "FLUZONE QUADRIVALENT"
          }
        ]
      },

####  Using UCUM codes in the [Quantity] datatype
{:.no_toc}

Both the [Vital Signs Profile] and [ Result Observation Profile] bind the `valueQuantity` datatypes to the [UCUM] code system.  A FHIR [UCUM Codes value set] that defines all UCUM codes is in the FHIR specification. This guidance specifies how to represent the Quantity datatype when the correct UCUM units are missing or the units are missing altogether which will likely occur in the real world.  

**UCUM code provided**

```
 "valueQuantity": {
    "value": 26.0,
    "unit": "g/mL",
   "system": "http://unitsofmeasure.org",
   "code": "g/mL"
  }
```

**free text units only**:
- If UCUM units are not available then represent units in the `unit` element.

```
 "valueQuantity": {
    "value": 26.0,
    "unit": "RR",
     }
```

**no units**

```
 "valueQuantity": {
    "value": 26.0
 }
```

### Representing Deleted Information

Clinical information that has been removed from the patient's record needs to be represented in a way so that client systems know they can delete them.

- A FHIR server SHOULD not delete resources.

- The resource status SHOULD be updated to the appropriate status such as  `entered-in-error` or `inactive`, and these resources SHOULD *still* be searchable by client applications.

- If the status is `entered-in-error`:

  - for patient viewing systems the content of resource SHOULD be removed. In other words a blank resource.

  - A provider facing system MAY be supplied with additional details that the patient viewing system would typically not have access to.

### Read(Fetch) resource notation:

Interactions on profile pages are defined with the syntax:

 **`GET [base]/[Resource-type]/[id] {parameters}`**

-   GET is the HTTP verb used for fetching a resource
-   Content surrounded by \[\] is mandatory, and will be replaced by the string literal identified.
    -   base: The Service Root URL (e.g. “<https://fhir-open-api-dstu2.smarthealthit.org>”)
    -   Resource-type: The name of a resource type (e.g. “Patient”)
    -   id: The Logical Id of a resource(e.g. “24342”)
-   Content surrounded by {} is optional
    -   parameters: URL parameters as defined for the particular interaction (e.g."?\_format=xml"}

For more information see the [FHIR RESTful API]

### Search Syntax

In the simplest case, a search is executed by performing a GET operation in the RESTful framework:

**GET [base]/[Resource-type]?name=value&...**

For this RESTful search ([FHIR Search]), the parameters are a series of name=\[value\] pairs encoded in the URL. The search parameter names are defined for each resource. For example, the Observation resource the name “code” for search on the LOINC code. See [FHIR Search] for more information about searching in REST, messaging, and services.

### Syntax for searches limited by patient

There are several potential ways to search for resources associated with a specific patient depending on the context and implementation. These searches result in the same outcome.:

1. An explicitly defined patient using the 'patient' parameter that controls which set of resources are being searched by resource type.  Note that all the search interactions in this IG are published using this syntax:
  - **GET [base]/[Resource-type]?patient=24342{&otherparameters}**
   - There are several variations to this syntax which are listed below:

        -   GET \[base\]/\[Resource-type\]?Subject=\[id\]{&other parameters}
        -   GET \[base\]/\[Resource-type\]?Subject=Patient/\[id\]{&other parameters}
        -   GET \[base\]/\[Resource-type\]?Subject.\_id=\[id\]{&other parameters}
        -   GET \[base\]/\[Resource-type\]?subject:Patient=\[id\]{&other parameters}
        -   GET \[base\]/\[Resource-type\]?subject:Patient=Patient/\[id\]{&other parameters}
        -   GET \[base\]/\[Resource-type\]?subject:Patient=\[https://%5Burl%5D/Patient/id\]{&other parameters}
        -   GET \[base\]/\[Resource-type\]?subject:Patient.\_id=\[id\]{&other parameters}
        -   GET \[base\]/\[Resource-type\]?patient:Patient=\[https://%5Burl%5D/Patient/id\]{&other parameter

1. The patient may be *implicit* in the context (e.g. using SMART). Then the patient parameter can be omitted:
  - **GET [base]/[Resource-type]{?other-parameters}**

1. Patient [compartment] based search with a specified resource type in that compartment. **NOTE this IG does not support compartment based searches**.

### Across Platform Searches

 servers are not required to resolve full URLs that are external to their environment.

### Guidance on limiting the number of search results

In order to manage the number of search results returned, the server may choose to return the results in a series of pages. The search result set contains the URLs that the client uses to request additional pages from the search set. For a simple RESTful search, the page links are contained in the returned bundle as links. See the [managing returned resources] in the FHIR specification for more information.

------------------------------------------------------------------------

{% include link-list.md %}
