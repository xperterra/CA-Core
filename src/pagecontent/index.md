### Introduction

This is a [FHIR](http://hl7.org/fhir) implementation guide that provides basic interoperability expectations for human-patient systems in the Canadian space.  Modeled after the US-Core implementation guide.

### Status

A **living document** including **scratch** notes and profiles captured while reviewing the [USCoreR4 Implementation Guide](http://build.fhir.org/ig/HL7/US-Core-R4/) against various Canadian sources, including:
- [PrescribeIT implementation guides](https://specs.prescribeit.ca/R2.0/)
- [Ontario Implementation guides](https://ehealthontario.on.ca/en/architecture/standards/draft), including:
  - [PCR](https://simplifier.net/guide/provincialclientregistrypcrhl7fhirimplementationguidev2.0/home), [PPR](https://simplifier.net/guide/provincialproviderregistrypprhl7fhirimplementationguide-v1.0/home), [OLIS](https://simplifier.net/guide/ontariolaboratoriesinformationsystemconsumerquery/home)
- [pan-Canadian HL7v3 specs](https://infocentral.infoway-inforoute.ca/extra/ca/mr0206-html/html/start.html)

The [GitHub repository for this CI build be found here](https://github.com/scratch-fhir-profiles/CA-Core).

### Principles

The following principles were applied when creating the profiles:
- *Focus on core content*
- *Be consistent* with other pan-Canadian standards where possible
- *Avoid arbitrary differences* between Canadian and US Core profiles to:
  - increase the opportunity for Digital Health / mHealth application reuse across North America
  - reduce developer / vendor effort to adapt to Canadian requirements
- *Only* impose constraints when strictly necessary

### CA Core Profiles

The list of CA Core Profiles can be found [**here**](https://build.fhir.org/ig/scratch-fhir-profiles/CA-Core/artifacts.html).

Each profile defines the minimum mandatory elements, extensions and terminology requirements that MUST be present. For each profile, requirements and guidance are given in a simple narrative summary. A formal hierarchical table that presents a logical view of the content in both a differential and snapshot view is also provided along with references to appropriate terminologies and examples.

Guidance, Capability Statements, and other have not yet been reviewed and added.

-----
Contact: [Russ Buchanan](mailto:rbuchanan@gevityinc.com)
