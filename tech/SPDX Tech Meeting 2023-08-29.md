# SPDX Tech Meeting 2023-08-29
 
## Attendees
* Maximilian Huber (TNG)
* Kate Stewart
* Gary ONeall
* Marc-Etienne Vargenau
* Jeff Schutt
* Sean Barnum
* Bob Martin (MITRE)
* Rob Craig
* William Bartholomew
* Gopi
* Jennie Kauffmann
* Jim Hutchinson
* Peter Monks
* David Kemp
 
## Agenda
* Documentation Status (William)
* Serialization of Namespace Map (Gary/Sean/William/David/Max)
* How to specify Mandatory Relationships (Sean/Alexios/Gary/Max) 
* Profiles - interpretations (Jeff/Gary) back to larger group
* Model Diagram - master to be updated with Profiles added 
 
## Notes
*  SPDX safety profile - linking evidence and enabling automation when bug fixes required.  
   * link to register: https://hubs.la/Q01_WzsS0
   
* Documentation 
  * All changes in spec parser done.   Using Ginger templates to generate content. 
 
* Namespace Map
  * PR that removed them: https://github.com/spdx/spdx-3-model/pull/411
  * Issue regarding intend of them: https://github.com/spdx/spdx-3-model/issues/485
  * Issue about conflicting information from Namespace Maps: https://github.com/spdx/spdx-3-model/issues/483
  * There’s also https://github.com/spdx/spdx-3-model/pull/431
   * Discussion of usecases to be supported (use case to focus on actors, goals, processes)
      1) Round tripping (document to document in multiple serialization formats going through model)
         * Document --> Document;    Document --> model --> Document
         * Simpler without multiple serializations formats.   What prioritize for 3.0?   Jeff:  more important for "a" serialization format.   From call:  Need to support multiple. 
      2) Same prefixes across multiple serialization formats
      3) Being able distinguish from million of elements in a database
      4) Support compaction in a semantically meaningful way
    * Actors - producer:A --> consumer/producer:B --> consumer C (same namespace map)
    
    * Two approaches:  serialization (pointing to model),  vs.  model.
       * Namespace map hint in serialization (serialization is supra model)
       * Have namespace map in model 
    * Each format has to have guideline how to share namespace map
 
A way to visualize the variants of the use cases:
| Use Case | Variants | Example |
| --- | --- | --- |
| Round Tripping | one serialization format, no model dependencies | document.json to document.json |
| | two serialization formats, no model dependencies |document.json to document.yaml |
| | one serialization format, data stored in model | document.json to graph database to document.json |
| | two serialization formats, data stored in model | document.json to graph database to document.yaml |
| Compaction in a semantically meaningful way | | |
| Maintain prefix across multiple serialization formats | | |
 
* Decision:  these are the use cases we want to support in 3.0
* Max: Have more than model or serializations for implementers to work with.  It's an implicit element that you can generate on parsing: Producer A creates document, Consumer/Producer B reads document A and may/may not create Element "X" containing document A's namespace map.   Gary:  Element may/may not get serialized.   
* Will be picked up in serialization meeting;  and brought back to this call next week. 
* Max to paste comments into these minutes.
 
* Mandatory Relationship 
  * In model spec today, certain relationships are expected to be required for conformance to specific profiles.   ie. licensing profile,  for "concluded license" relationship from artifact "to" license type.
  * We don't know how to express it in SHAQL.   What should it look like?  
  * Relationship:  Element A has concluded-license NOASSERTION;  and that must be present for Element A when profile X is asserted. 
  * Also from Max,  need to have scope around statement, so that can do merge    
  * Break into parts:   How can we provide the constraint?  How do we change the spec parser? 
    * Next steps:  Sean to take a pass at SHAQL for this
    * Example
      * From:  Software Artifact
      * Relationship: Concluded License ( 1:1)
      * To:  AnyLicenseInfo (ie. like License Expression | NONE | NOASSERTION)
      * Profiles that this can apply to:   Licensing, AI, Dataset
  * Open question is can we represent in JSON schema.  Max has concerns here. 
 
* Gopi: Just wanna add declared license can be 1:many
* Kate:  Yes Gopi - we’ll head to that after the constrained version (concluded license) is satisfied.
* Target by next Tuesday to have
 
## Action Items
*

## Next SPDX Tech Meeting 2023-09-05
