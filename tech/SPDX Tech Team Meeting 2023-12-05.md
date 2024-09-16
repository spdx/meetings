# SPDX Tech Team Meeting 2023-12-05

## Attendees
* Sean Barnum
* Rose Judge
* Nisha Kumar
* Jeff Licquia
* Alexios Zavras
* Maximilian Huber
* Karsten Klein
* William Bartholomew
* Joshua Watt
* Rob Craig
* David Edelsohn
* Dennis (Researcher at OIU; SBOMit)

## Agenda
* Updated model diagram(s) - Sean

## Notes

## Updated model diagram(s)
  * Core has been subbucketed into 3 buckets: 
      * Element Classes (Agent, Annotation, Relationship, ElementCollection, etc)
        * Can exist on their own
      * Non-Element Classes (CreationInfo, ExternalIdentifier, NamespaceMap, ExternalRef, ExternalMap, etc)
        * Inherent characteristics of some element; they would never exist on their own
        * Instances of these classes exist only to adorn single instances of Element classes through properties on those Element classes and cannot exist independent of such an Element class.
    * Simple Data Types
  * issuingAuthority in ExternalIdentifier should be String rather than anyURI as the issuingAuthority may often be simoly a name rather than a URI - Propose adding an issue to change in spec but leave as-is in diagram
  * ElementCollection has imports; it was moved to SpdxDocument; TODO: delete it from there
  * Annotation has contentType with cardinality 0:*. Should it be 0:1? TODO: Max to open a PR and discussion there
  * MediaType: String contrained to RFC 6838 - incorrect RFC? 6838 is the process for registering a media type. Should this be 2046? - TODO: open an issue to clarify
    * This was changed in commit: https://github.com/spdx/spdx-3-model/commit/cd13828e2ad97cf3127eb043d2e13c40cff9bf8b from David Kemp
  * DateTime: String new in diagram but was already in spec
  * ExternalRef `locator` was 1 but is 0..* in current spec - updated diagram to match spec
    * Interest in WHY this is 0
    * TODO: Open an issue to discuss why this is changed -- why would it be 0?
    * always was 0..*: https://github.com/spdx/spdx-3-model/commit/468bf0ba27e69081e3ec2a6c42bcf6bc4b216686#diff-7cefa29c744cf32f95f2b20f0a85042458d34edbc2a9fa696c04fd254a49b72cR25-R26
    * TODO: Spec needs to change `definingDocument` to `definingArtifact` in ExternalMap
    * LifecycleScopedRelationship `scope` cardinality is [0..1] which is consistent with the model
    * SpdxDocument cardinality for `dataLicense` property is [0..*] in the spec but was 1 in the previous model - ok with this?
      * `dataLicense` on SpdxDocument is defined as a `AnyLicenseInfo` type from core which does not exist. TODO: create an issue to fix SHACL - should reference `AnyLicenseInfo` from Licensing
  * https://github.com/spdx/spdx-3-model/pull/196 - some confusion from Sean about Artifact properties for a file. TODO: Sean will go review the PR and raise issues separately
  * All the enumerations have been updated
    * Pulled in all the different relationship types and tried to organize them into buckets - may need editing
    * LifecycleScopeType types are in spec but now added to diagram
    * Max suggestion to move examples off of the main digram
      * Counterpoint: Having small examples on the diagram is helpful for some
  * `begin` and `end` for PositiveIntegerRange are too generic and are likely to conflict with other use cases
    * TODO: They should be made more specific to this use such as beginIntegerRange and `endIntegerRange`
  * Licensing Profile
    * SimpleLicensingText is not used anywhere?
      * Joshua is using this frequently
    * TODO: ExpandedLicensing properties (`licenseComment`, `additionComment`, `additionName`, `licenseId`, `licenseName`, `additionId` and `seeAlso`) do not appear to be used anywhere?

* Security Profile
    * No noticed issues

* Build Profile
    * Straightfoward, no noticed issues
    * Build relationship types added to the Enumerations section on the Core diagram

* AI Profile
    * Properties constrained on Core or Software
    * No issues

## Model Generation/Site Generation update - Jeff
  * Current version put into example site for Open Compliance Summit demos
    * https://spdx3.licquia.org - just a demo; does not incorporate William's work which WILL be incorporated at a future date
  * All content generated directly from the GitHub model using MkDocs
  * Lite profile is still a PR, has *not* been merged but it is listed in the demo for OCS
  
* SHACL model not validating
  * We need a generated website first - MkDocs first but RDF second
  * Anything that stops these being doing in parallel?

## Open PRs/Issues
* Issue 561 Add Software Level of Support property to Software Package
* See comments on issue.
* Issue 562 Missing license cross reference properties.
* No concerns, assigned to Gary.

## Decisions
*

## Action Items
* Open an issue to discuss why this is changed -- why would it be 0?
    * always was 0..*: https://github.com/spdx/spdx-3-model/commit/468bf0ba27e69081e3ec2a6c42bcf6bc4b216686#diff-7cefa29c744cf32f95f2b20f0a85042458d34edbc2a9fa696c04fd254a49b72cR25-R26
* Spec needs to change `definingDocument` to `definingArtifact` in ExternalMap
* Create an issue to fix SHACL - should reference `AnyLicenseInfo` from Licensing
  * https://github.com/spdx/spdx-3-model/pull/196 - some confusion from Sean about Artifact properties for a file. Sean will go review the PR and raise issues separately
* `begin` and `end` for PositiveIntegerRange are too generic and are likely to conflict with other use cases. They should be made more specific to this use such as beginIntegerRange and `endIntegerRange`
* ExpandedLicensing properties (`licenseComment`, `additionComment`, `additionName`, `licenseId`, `licenseName`, `additionId` and `seeAlso`) do not appear to be used anywhere?
* Open an issue for clarification on the change from RFC 2046 to RFC 6838 standard 
* Discuss and resolve issues marked as todos in the diagram 
*  Update spec with 'defining document' changed to 'defining artifact' 
* Decide whether life cycle scope pipe relationship's cardinality should be updated or left unchanged in current spec 
* Review new properties added under artifact class for build profile usage 
* Resolve naming issue with positive integer range class properties 'begin' and 'end' 
* Remove notes on diagrams once issues are resolved 
* Spread a PR with new diagrams and sub-diagrams on GitHub 
* Update text regarding red properties in Artifact discussed in core but not unique to security 
* Visualize build profiling by putting relationships into a diagram 
* Submit packaging parts as PR for spec parser 

## Next SPDX Tech Team Meeting 2023-12-12
