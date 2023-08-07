# SPDX Tech Team Meeting 2023-07-25

## Attendees
* Alexios Zavras
* Armin Tänzer
* Bob Martin
* David Edelsohn
* David Kemp
* Dick Brooks
* Gary O'Neall
* Holger Frydrych
* Jeff Schutt
* Jennie Kauffmann
* Karsten Klein
* Kate Stewart
* Marc-Etienne Vargenau
* Maximilian Huber
* Nisha Kumar
* Norio Kobota
* Prasad Iyar
* Rob Craig
* Rose Judge
* Sean Barnum
* Takashi Ninjouji


## Agenda
* Review security diagram to be used as base for other profiles' examples (Rose + Jeff) (15 minutes)
* SPDX-Lite
  * Background and context - requirements: https://github.com/OpenChain-Project/OpenChain-JWG/blob/master/subgroups/sbom-sg/outcomes/SPDX-Lite/Proposal_v3.0/model/LiteProfile-Requirements.md
  * Determine how to describe required field restrictions for the SPDX-Lite fields for the lite profile.  Reference current     pull request: https://github.com/spdx/spdx-3-model/pull/350 
  * Determine how to document “these are the only fields you need to worry about” – reference current SPDX Lite annex: https://spdx.github.io/spdx-spec/v2.3/SPDX-Lite/ 
  * Discuss serialization relationships to the SPDX Lite proposal and frame up follow-on work for the serialization team   
    * Is the SPDX Lite related to the open issue on REUSE file tags? (https://github.com/spdx/spdx-spec/issues/856)  
    * Is SPDX Lite related to the serialization discussions on a simpler format, like tag/value? 
* Closing off the open PRs

## Notes
* Security Diagram
  * Rose went through the diagrams in .drawio
  * Nisha is going to try this with build
  * Kate suggested that we unify the symbols with the ones that the Safety Committee is using to represent use cases.   Rose & David are supportive.   AI:  Kate to share (DONE:  https://docs.google.com/presentation/d/1H5WJonJYRsn-FekY5GTvCadES3dO6a66GqMf-iiTJec/edit#slide=id.g2011ae1ff0e_0_0)
  * Properties:  Normalizing on certain keywords - use camel case for consistency. with spdx-3-model files
  * Relationships:  might be useful to show have properties.
  * Multiple assertions:  Weight of arrows - more detail. 

* SPDX Lite
  * Allow profile that restricts properies on existing classes.
  * What is the policy on additional items?  "It should be "at least", and don't care if other properties are present.
  * These fields must be there to be "sufficient" for adhering to SPDX-Lite.   Allowed - can ignore and still have an application that complies. 
  * Cross check that the validatators for SPDX document will need to work with SPDX Lite documents.
  * Applications that only support SPDX-Lite don't need to process other fields.
  * Reminder profiles can only make things more restrictive. 
  * Definitions:
      * Profile Team - used as areas of interest,  organizing into teams.
      * Profile Namespace - grouping together "new" classes, properties & enumerations.
      * Profile Conformance Point - Additional restrictions on the model that state if you claim to support the profile, then you must conform to these aspecifications.   Fields may be in same namespace, or not in the same namespace.
* There's a profile conformance point for software for instance.
* SPDX Lite -->  separate NTIA minimum conformance point + separate subset of licensing profile conformance point. 
*   Discussion about separate SPDX Lite into satisfying two different conformance points (NTIA & Licensing).
* How to specify conformance points to not have namespace properties?  Want to create a profile conformance point that only uses the existing classes. 
   * Profile conformance point without any new classes.  
   * How should this be written up?   Alexios:  Put it in the top level profile file,  as <profile>.md;  see software example. 
   * Sean: SHACL is the right way to specify conformance requirements. Shapes can be expressed against any classes/properties in any namespace.  The additional constraints for each profile should be specified independently of the non-profile classes and shapes they apply to.   
   * Max:  Property is from Core Element, and then have ...
   * David:  just add restriction to existing element (example "name")
   * Jeff: Ensure conformance to a profile namespace, but not sure solving conformance acrsos multiple profiles.
   * Nisha: Build profile looking for way to restrict relationships.   Can we use external property restrictions.    Gary:  let's figure out Name for now, then take it to this. 
   * Sean: David is correct if you want to apply the name required constraint on ALL Elements. If you want to require it on Person but not on Package then you need to specify a property shape for each situation where each shape involves both the specifify Class and the proeprty
   * Gary:  In a shape, it has to say class name & property.    If you know the property, you know the class it goes to.   Interpreting this as namespace full into URI for name.
   * Gary:  Still allow to be in either place?   Alexios: Yes.
   * Gary: So would do it as an SPDXLIte.md file at the SPDXLite profile.    
   * Kobota: /Core/Element/name or /Software/Package/name inherited from Core class?   Only packages should have names, so should be /Software/Package/name. 
   * David: if just talking about one class, add the restriction. 
   * Japan team to update the PR to reflect this new way of describing the profile-level .md file
* How do we publish sufficient fields? 
   *  Propose we just create an annex - like before,  but we need to put this into generation for Annex.
   * Should each of the profiles be an annex? 
   * Follow up with William on mechanisms
   * Kate:  Document as Clauses as Profile Namespace (ie. new fields) and Annex is Profile Conformance point (fields expected)

## Decisions
* Agree to head towards enabling profile conformance point made up of restrictions to existing classes and properties. 
* Support "External properties restrictions" on profile-level .md files
* New Definitions: 
      * Profile Team - used as areas of interest,  organizing into teams.
      * Profile Namespace - grouping together "new" classes, properties & enumerations.
      * Profile Conformance Point - Additional restrictions on the model that state if you claim to support the profile, then you must conform to these aspecifications.   Fields may be in same namespace, or not in the same namespace.

## Action Items
* Kate to share symbol diagram:  DONE:  
* Japan team to update SPDX-Lite PR
* Alexios to create an issue on how the profile-level .md file is to be documented.
* Follow up with William on how we handle spec changes.

## Next SPDX Tech Team Meeting 2023-08-01
