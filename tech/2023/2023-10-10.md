# SPDX Tech Team Meeting 2023-10-10

## Attendees (13)
* Gary O'Neall
* Alexios Zavras
* Rob Craig
* Rose Judge
* Sean Barnum
* Joshua Watt
* Jim Hutchison
* Jeff Schutt
* Kate Stewart
* Takashi Ninjouji
* Max Huber
* David Edelsohn
* David Kemp
* Nisha Kumar

## Agenda
* Kate- Relationship proposal to be reviewed
* William- documentation update
* Gary- Follow-up from Serialization meeting: 05 October
* Gary- Corrected root description discussion.
* Gary - Proposal to move data license to "XCollection" a.k.a. "SerializableCollection" a.k.a. "SpdxDocument"

## Notes
* Alexios reworked spec parser. Should be ready next week for testing. 
* https://github.com/spdx/spdx-3-model/pull/447 - 
* The new spec parser will create documentation which may be sufficient for 3.0

### Relationships
* Issue with diagram not being up to date
  * Currently, no plan to update diagram
* We may be able to remove some of the relationships based on new classes in the model
* Kate is mapping the new relationships to the previous relationships
* AssessmentRelationship is in the diagram, but not in the model
  * Should we add AssessmentRelationship and make the VulnAssessmentRelationsihp a subclass of AsssessmentRelationship to the diagram
  * AssessmentRelationship would be valuable, but it isn't "fully baked"
  * Agree to remove AssessmentRelationship from the diagram in 3.0, VulneAssessmentRelationship already subclasses directly from relationship - we will consider adding AssessmentRelationship back in 3.1
* Discussion on the subclasses of Relationship
  * If there are additional properties, we would have a subclass
  * There is a lot of repeated text between similar subclassess
  * General agreement to shorten the name with the caveat that we need to know what the class represents
  * Agreement to stick with what we have
* Question on LifecycleScopedRelationship [?]
* Question on completeness
  * What is the default on completeness - Agree to update the text that no conclusion can drawn if no value is present
* Question on whether we can represent the known unknowns for all use cases when we removed the reverse direction
* What do we do when we have A dependes on B marked complete and a separate relationship A depends on C marked complete - what do we do?
  * This is inconsistent
  * It is good to "shine a light" on the inconsistency
  * It would be nice to validate this - we can create SHACL
  * We should document this and how it should be handled
* What do we do with multiple relationships which overlap (e.g. same from and same type with multiple relationships)
  * should we have this be on the ElementCollection?
    * Benefit it reducing the possibility of conflict
    * Cost is that independent analysis scenerios can not add relationships
  * Factors impacting analysis: CreationInfo creator, CreationInfo time, within the same ElementCollection, with the exact same CreationInfo
    * With the exact same CreationInfo is a stronger class - may it doesn't matter if they are in the same ElementCollection
  * Proposal: Document these in a "best practices" document.  Reasoning: the model is OK, it represents inconsistencies that can happen in the real world and we should document how the model represents the real world and document reccomendations on how to deal with the real world inconsistencies
* Question on annotations - where we use this
  * Audit secenario - annotate with Review type
  * Should we change Annotation to a relationship type?
    * Decision - no - keep Annotation - in use today
* Question on linkType and requirement properties - should they be move them into the core profile classes
  * Would moving it be a breaking change?  no
  * There could be overlap of the linkType with hardware
  * Consensus that the hardware link types are not "baked enough"
  * General agreement that the vocabularies for the link type will be disjoint between hardware and software
  * Decision: Keep as is for now and revisit in 3.1
* Need to document when relationshiptypes can be used with lifecycle types
  * Should this be in the spec?
  * Proposal that the lifecycle scope constrains the relationship types
  * Do we add and assessment type to LifeCycleScopeType?
    * would lead to further confusion with assessment usage in the spec
    * suggest different name - audit, review
    * Proposal add "audit" enumeration to LifecycleScopeType
* Overlap between SbomType and LifeCycleScopeType
  * One applies to an SBOM (ElementCollection) and one applies to the lifecycle of the Element
  * Agree that we have 2 properties
  * General agreement we should move to one type if possible
  * Start with the SBOM type - see if that works, then rename and have both properties point to the same type
  * Should we add deploy to LifeCycleScopeType?
* Discussion on Licensing of X-Collections
   * Example of Translating a book.   
   * Want to describe license in serialized bunch of stuff
   * Jeff: Want to be as atomic as possible, so don't leave holes.   
   * Gary will bring this input into the licensing discussion this afternoon and report back to the serialization team tomorrow

## Decisions
* Agree to remove AssessmentRelationship from the diagram in 3.0, VulneAssessmentRelationship already subclasses directly from relationship - we will consider adding AssessmentRelationship back in 3.1
* Agree to keep Annotations as a separate class
* Keep the linkType as is - consider a hardware profile and a potential core superclass in 3.1

## Action Items
* Update documentation on completeness property to document that the lack of a values implies that no conclusion can be drawn
* Update documentation on the completeness property to describe what completeness means when we have multiple relationships with the same from and same relationship type and completeness type complete - this can be allowed to exist in an SPDX document but should be flagged as an issue.
* Add PR proposal add "audit" enumeration to LifecycleScopeType
* Add a PR to propose using the same SBOM type for both the SBOM type property and the lifecycle scope property
* Build team needs to update the relationships to include LifeCycleScope- Nisha & Joshua
* Gary to discuss data license for individual elements serialized

## Next SPDX Tech Team Meeting 2023-10-17
