## SPDX Tech Team Meeting 2023-08-01

## Attendees:
* Sean Barnum
* William Bartholomew
* Dick Brooks
* Kevin Conner
* David Edelsohn
* Maximilian Huber
* Yoshiuki Ito
* Karsten Klein
* Jennie Kauffmann
* Nisha Kumar
* Rose Judge
* David Kemp
* Norio Kobota
* Nisha Kumar
* Bob Martin
* Peter Monks
* Gary ONeall
* Kate Stewart
* Joshua Watt

## Agenda
* SPDX-Lite questions - 15 minutes
* Follow-up discussion on JSON-LD serialization review - do we require all "objects" to have full URI's or do we allow blank nodes?
* Relationships review
* Discuss SBOM and SpdxDocument relationship: https://github.com/spdx/spdx-3-model/issues/415
* Discuss profiles and collections: https://github.com/spdx/spdx-3-model/issues/365

## Minutes

### SPDX Lite
* Topic: SPDX lite
  * Team had drafted a lite profile but had some questions
  * Questions:
      * Licensing profile was updated recently with Custom License and Simple License. Which one to use when restricting licenses in the Lite profile?
      * Gary: may want to use the Simple Licensing profile and within that there is a license expression property or the AnyLicenseInfo which can be a license expression or the complex license. SimpleLicensing text could be included.
      * Max: still struggling with the relationship(?)
      * Gary: there is a PR to change the Declared and Concluded license from SPDX2 to Relationships.
      * PackageFileName is now a relationship(?). Sean proposed a SHACL(?) shape for the relationship.
      * Sean: The idea is to represent the "PackageFileName" as a "Package" object, a "File" object and a relationship between the two.
      * Follow up: issue 83

### Blank nodes discussion
* In the current JSON-LD examples (e.g.https://github.com/spdx/spdx-3-model/blob/main/serialization/json_ld/examples/converted_from_spdx_2.json) blank nodes are used for any "non-domain" models (e.g. CreationInfo, ExternalReference)
* Sean has concerns about the use of blank nodes
* According to a google search, Consensus among some of the academics blank nodes are problematic
  * One of the problems is that it is inconsistently defined in the specification
  * Example of blending graphs with blank nodes - non-unique ID's
* William - can we pull this down to how we are using this in SPDX?
  * Previously we split the concepts of "simple" and "complex" data types - where we treat simple data types as being the same if all properties are the same
  * Can we have a specific example
* Sean - Simple example - CreationInfo - 2 elements have creation info that went into blank nodes get blended into a graph, if they are not globally unique they get resolved to different creation info's than intended
  * Solution is to skolomize: https://en.wikipedia.org/wiki/Skolem_normal_form
    * Issues with this approach - if ingestion doesn't consistently skolomize then we have issues
* Max: Question - is there another issue that you can not link if you don't have a globally unique ID
  * Hash's will also have a globally unique ID
  * Would like to have the benefits and other downsides
* Sean: for hash, any "element" should have a globally unique ID, you don't know what the content is in the graph, you can generate a globally unique ID - example - you could have 3 different hashes associated with that ID, 
* William - explain how 3 different hashes could be associated with one package with skolomization?
* Sean - skolomization solves the issue
* Gary: [missing comments] - agreed that there are reported issues blank nodes, but none apply to SPDX, have been using blank nodes for more the 10 years with no reported issues
  * We agreed months ago on only having globally unique ID's for elements
* Sean - never agreed to restricting globally unique ID's
* David: Elements are in the graph, datatypes are not in the graph
* Sean: The graph is all of that together - example of checksum
  * The object in the graph always has an ID
  * No consistency for skolomization
  * The fact that a hash is unique has no bearing on it being in the graph
* David: verifiedBy - compound data types
* Sean - they are all objects with an ID which can be globally unique or blank
* David - we don't intend to create globally unique ID along with values for an object
* Sean - we could focus on the quesiton of producers producing globally unique ID or consumers skolomizing in ingestion
* Bob - is the lack of issues in 2.X related to scope?
* Gary - probably more related to SPDX 2.X consistent use of skolomization
* William - is skolomization workable with blank nodes?  Is it acceptable?
* Sean - rephrases William's question - can it be done if not why vs should it be done if not why?
* Sean - option 1 use blank nodes with skolomization, option 2 producer always produces unique ID's
* William - would like to answer the "can" question first.
* Nisha - Is this scoped just to JSON-LD?
* William - no - applies to evertything
* Nisha - request that we "dumb down" the descriptions so we could have broader participation
* William - provided a desciption
* Sean - wants to go down the compare path
  * Described advantages of generating globally unique ID
* William described downside to using globally unique ID - verbosity, etc.
  * The whole point of not making non-element's non-global ID's 
* Sean - generating IDs was discussed and it ensures global uniqueness. UUID collision may occur but not an issue for complexity.
* William - this means we are implementing skolomization. Sean - yes, we can implement but we can also avoid this if everything was an element. That means everything has an id and can be transferred across serialization.
* William: this is just a complex datatypes. Sean: no these are objects. Instances of a class.
* Sean: if objects are linked, we want to ensure that deleting one object deletes all the linked objects.
* William: compaction is way more valuable than the risk of creating orphaned objects. Sean: it actually affects compaction and expansion as the data will get lost.
* David: alternatives - complex datatypes have no nodeIDs. Producer assigned global IDs, and Invisible global IDs. You can do a SHACL search. The model can handle this properly
* Sean: sparql execution engines want a globally unique ids or else it can't find anything. David: does not agree and will look up that reference again.
* Nisha: I get the feeling these conversations are biased towards existing tools that work with rdf and json-ld exclusively 
    * Gary: it generally applies to all serialization.
* David: https://www.w3.org/TR/rdf12-schema/#ch_collectionvocab an RDF "Collection" (i.e. not SPDX Collection which is an RDF "Container")  has: List, First, and Rest (i.e. Complex Datatype without an object ID)
* Next step:  Sean to provide SPDX centric examples on how it will break SPDX?   Will make it more difficult, but prevent some capabilities.
* Looking for examples at:  Linked data question and ID5 question. 
* Concern points agreed to:  Hurts compaction,  bloats out document. 
* IDs for these groupings,  and why 
* David would like to see:  Snippet element with positive data range (positive integer range) doesn't have an object id (using RDF collection) - Complex data types without object ids.
* Request to think if we can explore if we can adding these in 3.1.   

## Next meeting agenda
* Continue discussion on blank nodes
* Discuss snippetsFromFile property https://github.com/spdx/spdx-3-model/issues/130
* Close on verifiedUsing for packages: https://github.com/spdx/spdx-3-model/issues/345
* Discuss packageFileName https://github.com/spdx/spdx-3-model/issues/83
* Discuss RDF namespace related issues - https://github.com/spdx/spdx-3-model/issues/434, https://github.com/spdx/spdx-3-model/issues/439, https://github.com/spdx/spdx-3-model/issues/438
* Discuss packageFileName issue: https://github.com/spdx/spdx-3-model/issues/83
