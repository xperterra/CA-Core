### Introduction

This 'implementation guide' is a **living document** containing **scratch** notes and profiles captured while reviewing the [USCoreR4 Implementation Guide](http://build.fhir.org/ig/HL7/US-Core-R4/) against various Canadian sources, including:
- [PrescribeIT implementation guides](https://specs.prescribeit.ca/R2.0/)
- [Ontario Implementation guides](https://ehealthontario.on.ca/en/architecture/standards/draft), including:
  - [PCR](https://simplifier.net/provincialclientregi), [PPR](https://simplifier.net/provincialproviderre), [DHDR](https://simplifier.net/ontariodigitalhealth), [OLIS](https://simplifier.net/ontariolaboratoriesi)
- [pan-Canadian HL7v3 specs](https://infocentral.infoway-inforoute.ca/extra/ca/mr0206-html/html/start.html)

The intent is to begin to provide an initial, draft set of FHIR profiles that can be refined
into a set of Canadian baseline profiles similar to the US-Core.

The [GitHub repository for this CI build be found here](https://github.com/scratch-fhir-profiles/CA-Scratch).

### Principles

The following principles were foundational to the analysis:

- Be consistent with other pan-Canadian standards where possible, and
- Avoid arbitrary differences between Canadian and US Core profiles to:
  - increase the opportunity for Digital Health / mHealth application reuse within North America
  - reduce developer / vendor effort adapt to Canadian requirements
- Do not impose constraints unless strictly necessary
- Focus on core content

### Content

The following **scratch content** has been developed so far:

#### Profiles

{% include list-simple-profiles.xhtml %}

#### Extensions

{% include list-simple-extensions.xhtml %}

### Note

Guidance, Capability Statements, and other have not yet been reviewed and added.

----

Contact: [Russ Buchanan](mailto:rbuchanan@gevityinc.com)