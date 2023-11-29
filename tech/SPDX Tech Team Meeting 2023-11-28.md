# SPDX Tech Team Meeting 2023-11-28

## Attendees
* Jeff Licquia
* Rob Craig
* Kate Stewart
* Bob Martin
* Peter Monks
* Max Huber
* Alexios Zavras
* Karsten Klein
* Nisha Kumar
* Gary O'Neall
* Rose Judge
* David Edelsohn
* Peter Monks
* Arthit Suriyawongkul
* Dick Brooks

## Agenda
* Jeff: Status of the Spec Document generation? (William, Alexios, Jeff)
* Bennett: Updated UML model diagram? 
* Kate: discussion on completeness
* Gary: PackageUrl vs PackageUri - how handle private packages inside org that can't have PURL.  

## Notes
* Toolstypscript project in SPDX org (https://github.com/spdx/tools-ts)
   * Can be used in whole nodeJS ecosystem
   * Focused on being lean and lightweight - generates sensible core of SPDX annotations.
   * Sufficiently supported to be usable to generate SBOMS
   * Plugin for yarn? & Rollup projects available 
   * Published first version to NPM registry - version 0.0.4. - Looking for Feedback
   * Reimplemented NPM with new library;  future task.
* Website with SPEC
   * Jeff - Should go ahead with merging Alexios & William's work?   Goal to get website up before next week.
   * Alexios hasn't heard from William- so no progress to date.   
   * William's demo of generating website off the site,  Jeff to poke William.
   * SPDX 3 model - generated from ontospy - add into site.
      * Auto generated pages of the model.    GH: SPDX3 model.
      * Do the work outside of the spdx-3-model; but need to figure out how to trigger when the model changes; it triggers the rebuild of the spec.   
* UML model 
  * Bob to ask Sean on Friday if can generate version from spec.
  
### Relationship Completeness
* Relationship completeness
* Default would be "incomplete" - previous decision - based on analysis of uninioning of relationships
* Some scenarios are not clear how it is handled
* Nisha - Why is there a noassertion if there is an "incomplete" as the default
* Max - this is always in the context of a surrounding collection, if something is added later, it would be a different SBOM/Collection, so there is no conflict
* Kate - Not currently documented that it is in the context of a collection
* Alexios - what are the definitions of incomplete / noAssertion?
  * Looking at current definitions: 
    * Update RelationshipCompleteness.md to add a description to be explicit rephrase to be clear that incomplete is known to not have everything
* Need to document the context of relationship in a collection
  * Document in Relationship.md description
  * Document in RelationshipCompleteness.md description
* Kate to generate a logic table with expected outcome of assertion, no
* Incomplete should be the default for relationships unless someone asserts completeness.
* Incomplete relationships should always be viewed in the context of a collection.
* Incomplete means it is known to not be exhaustive.

### PURLs - Package URI & URL
* Package URLs are optional;  proprietary package that doesn't confirm to scheme. 
* Artifact URL - superset of Package URL  right now.
* Satisfying the NTIA minimum for Unique ID need to have Namespace+SPDXID.
    * Collisions and vagueness of PURL specification is part of issue. 
    * Lack of specificity on how to deal with proprietary.
    * FYI: https://github.com/package-url/purl-spec/issues/242 : discussion around PURL and issues with using them as unique identifiers
    * We still need folks to weigh in on https://github.com/spdx/spdx-3-model/issues/493 regarding package URL
    * Referred to as URI vs. URL
    * Conclusion: Agreement to use Package URLs when we can.   
        * When we can't, can we choose another unique ID or use SPDXID URI?
        * Spec requires all element have an ID which any URI - so just SPDXID URI
    * Arthit noted for improving PURLS there's a project from W3C Permanent Identifier Community Group: https://github.com/perma-id/w3id.org 

* Persistent Uniform Resource Locator name spaces clashes with Package URL. https://github.com/spdx/spdx-3-model/issues/493
  * https://github.com/package-url/purl-spec uses itself both `purl` and `package URL`
  * 2.3 uses PURL for Package URL
  * In RDF it's got a purl.org 
  * For 3.0 --> Change property name to packageUrl (https://github.com/spdx/spdx-3-model/blob/main/model/Software/Properties/packageUrl.md)
  * For 3.0 --> Change (current) pkhUrl to packageUrl as an external identifier type https://github.com/spdx/spdx-3-model/blob/main/model/Core/Vocabularies/ExternalIdentifierType.md
  * For 3.0 --> We have IRI already there, and this can refer to the persistent uniform relocators. 

### PRs
* #558 (merged) - has 3 approvals.
* #517 - has been updated based on last week. 
* #503 - Extension. - Waiting for Sean to update
* #498 - Ingerity method - no verified using for packages.   (Queue up for Dec 12th meeting - needs Jeff)
* #492 - Deletes's ExternalID.md (Queue up on Dec 12th meeting - needs Jeff, Alexios, Gary).
* #490 - Needs conflics resolved.    Gary to take a pass.   Then looking for 2nd reviewer (Max?, Alexios?, Nisha?)
* #488 - Reviewed in call, all agreed looks reasonable.    Conflict needs to be resolved and then it can be merged.
* #452 - dataLicense is now part of Collection, so remove from Core (on every element).    Need input from Steve & Jilayne;  delay rc2?

## Decisions
* We use SPDXID URI as the unique identifiers, but encourage folks to fill in the optional PURL field when information is known. 
* Update PURL to be PackageURL in 3.0 Spec 
* auto-generated site from the spec should be integrated into GH
* Jeff proposed that he take over William's Python infrastructure work
* Sean to work on the UML diagram
* update the model to document that relationships happen within the context of a collection
* Move the milestone changes to the collection instead of every element and relationship

## Action Items
* Max to forward email to Kate on the JavaScript / TypeScript library - Kate will forward to NodeJS ED to ask for help testing
* Alexios to send details of the document developement flow in mind to Jeff.
* Kate to replicate the table of when you union relationships - w.r.t. completeness
* Max will generate a pull request to document the collections context is needed for completeness
* Gary to resolve #490 merge conflicts
* Alexios to merge in the new parser.   Doesn't generate RDF, but will be implemented.
* Rose to make change to PackageURL
* Update UML model
* Get together to reconcile problems with the spec anim sheet
* Work on the UML model diagram
* Create pull request for updating contact method descriptions
* Generate a pull request on a collection of contacts for completeness
* #498 - Ingerity method - no verified using for packages.   (Queue up for Dec 12th meeting - needs Jeff)
* #492 - Deletes's ExternalID.md (Queue up on Dec 12th meeting - needs Jeff, Alexios, Gary).
* #490 - Needs conflics resolved.    Gary to take a pass.   Then looking for 2nd reviewer (Max?, Alexios?, Nisha?)
* #488 - Reviewed in call, all agreed looks reasonable.    Conflict needs to be resolved and then it can be merged.
* #452 - dataLicense is now part of Collection, so remove from Core (on every element).    Need input from Steve & Jilayne;  delay rc2?
* renaming of a package URL
* Update the description for the completeness of the model
* Gary/Kate out next week (Japan); Rose to run 2023.12.05 meeting. Kate to ask William if he can assist in hosting.

## Next SPDX Tech Team Meeting 2023-12-05
  * #498 - Ingerity method - no verified using for packages.   (Queue up for Dec 12th meeting - needs Jeff)
  * #492 - Deletes's ExternalID.md (Queue up on Dec 12th meeting - needs Jeff, Alexios, Gary).
