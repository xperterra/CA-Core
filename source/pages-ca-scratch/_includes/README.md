# CA-Core-YAML

These are [YAML](https://yaml.org) representations of the HL7 FHIR profiles used in the [CA-Scratch](https://github.com/scratch-fhir-profiles/CA-Scratch) 'implementation guide'.

### Rationale:
Authoring profiles using YAML:
- is (relatively) human friendly,
- allows authors to capture comments inline during editing, and
- is *very* easy to convert to JSON for publishing.

### Use:
These are part of work process supported by two scripts:

1. **Script 1:** Pulls a resource (JSON artifact) directly from https://www.hl7.org/fhir, converts it to YAML, localizes the resource metadata, comments out the structure definition and strips back some content unnecessary for profile editing;

2. **Author:** Edits constraints and extensions by hand in YAML; and  

3. **Script 2:** Converts the updated YAML file to JSON, runs JSON schema validation on the resource and pushes it to the CA-Scratch repository for publishing.

Note:
- Comments (and commented out structure definition) in the YAML document are not carried into the JSON artifact during conversion and publishing of the Profile.
- This work process has (so far) supported this analysis but it has not been fully and properly tested.
