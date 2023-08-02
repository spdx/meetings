# SPDX Serialization Team Meeting 2023-07-27

## Agenda
- can multiple elements in a serialization refer to same (non-Element) data without replicating them?
- related: what can we use for compaction on serializing common info (e.g. CreationInfo)

## Attendees
* Alexios Zavras
* Armin Tänzer
* David Kemp
* Gary O'Neall
* Jonathon Gardner
* Karsten Klein
* Maximilian Huber
* Nisha Kumar
* Sean Barnum

## Notes

a second, related question: can we use blank nodes? will be discussed next tue on tech call

- can multiple elements in a serialization refer to same (non-Element) data without replicating them?
- we can still "share" data while in a serialization without not automatically "sharing" in the logical model
- criteria to choose whether a proposal is accepted: accuracy and precision
- agreement that these criteria are met with the proposal
- checking about simplicity/complexity
- this is about the proposal being possible / a valid serialization,  not being mandatory
- it could be implemented by the original producer or by a filter compacting the data
- Gary points out the common case of 
- no disagreement that it is simple enough (for now)

## DECISION(s): 
- (tentative) we allow this compaction proposal

### blank nodes 

- Alexios:
  - blank nodes are an integral part of RDF definition; we cannot blindly forbid them
  - if we mean that every JSON object has to have an @id, we should change the model and add the id property to all "complex data types"
  - we are discussing whether id's may be "locally-unique" (in the context of one document) rather than always be "globally unique" (full IRIs)
  - "locally unique" id's are under the "_" (blank) namespace
- Nisha worried about lookup of indirect info. But lookup is the same when using any (local or global) identifiers
