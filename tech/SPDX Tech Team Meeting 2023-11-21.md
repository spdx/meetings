# SPDX Tech Team Meeting 2023-11-21

## Attendees
* Rob Craig
* Bob Martin
* Arthit Suriyawongkul
* Jeff Licquia
* Nisha Kumar
* Kate Stewart
* Sean Barnum
* Joshua Watt
* Alexios Zavras
* David Edelsohn
* Victor Lu
* Karsten Klein
* Maxmilian Huber
* Dick Brooks

## Agenda
* Relationships (Kate, Joshua, William)
* Build Profile Cleanup (Nisha, Joshua, Kate)
* AI Profile Cleanup (Kate, Alexios, Gopi?) 
* Extension point (Alexios, Sean, William)

## Notes

## Relationships
* The group discussed removing redundancies in their relationships, including the relationship model, life cycle relationship, software dependency relationship, and license scope relationship.
* table of relationships: https://docs.google.com/spreadsheets/d/1yb49TkcR_dVEH_k_iOcBjNZbYDjkmd0HVweIuDpS9eg/edit#gid=133189817
* relationahsip model https://docs.google.com/presentation/d/1eWdUVgReis3suuLWOOTNIkwWfK-inZy9th4QDUBpfm0/edit#slide=id.g230cd25f062_0_0 
* we want LifecycleScopedRelationship; the Software-specific relationships are confusing for now, leave them for later
* config: configures/hasConfiguration alternatives
* configuring relationships in software: discussion about making from and to fields in relationships interchangeable to make the relationship bidirectional.
* Sean proposed having two separate relationship types to avoid ambiguity.
* Kate suggested moving forward with the configuration and considering it as a deferral request.
* Dialogue about the redundancy of bid profile in the software.
* Metafile renamed to Metadata; directionality to be decided
* Decision was made to defer software dependency relationships, software dependency link type, and software dependency conditionality type.
* The uncertainty regarding the configurations led to the decision to revisit it later.
* object relationships discussion: marking relationships as complete or incomplete, based on the presence of all children.
* Top-down and bottom-up relationships were considered necessary for different use cases.
* Kate provided updates on various topics, including historical affiliations and the simplification of relationships.
* Discussion about dynamic links and static links.
* Build profile: https://github.com/spdx/spdx-3-model/pull/517 - revise?  Yes,  Nisha will. 

* AI profile:  https://github.com/spdx/spdx-3-model/pull/536 - merge?   
   * Alexios & Max are ok;  ok to merge.

* Extension point:  https://github.com/spdx/spdx-3-model/pull/503 - next steps
  * note: not directly on element, unless "profile" applied.    Element object would have an extension property when the profile is asserted. 
  * a consumer, should not need to worry about extensions.   
  * Property moves to core with "optional"    Next steps - Sean to adjust PR.
  * Keep as independent profile;  its the validation of profile that enforces the shape.
  * Add conformant rules for the extension profile "must be at least one extension in the profile"

## Decisions
* Defer introduction of SoftwareDependencyRelationship and the corresponding
SoftwareDependancyLinkType and DependancyConditionalityType 
* keep both top-down and bottom-up relationships for accommodating different use cases
• use the from and to fields interchangeably to make the relationship bidirectional for faster configuration
• follow the lead up to the branch role rather than going to the branch lead
• have at least one extension in one element
• leave optional pronouns and dependencies as they are for now

## Action Items
* Kate: next meeting discussing completeness.
* #556 OK to merge

## Next SPDX Tech Team Meeting 2023-11-28
