# SPDX Serialization Meeting 2023-10-05

## Attendees
* Gary O'Neall
* Max Huber
* Nisha Kumar
* David Kemp
* Sean Barnum
* Jeff Schutt

## Agenda
* Review proposals on how we bring all the issues together

## Notes
* discussion of PR #509, introducing Serialization specifications
  * https://github.com/spdx/spdx-3-model/pull/509 
  * Question: do we agree on the general structure
    * yes, it looks good
  * Discussion of XCollection in context of the model
    * it is currently deriving from Bundle
    * Proposal to have it derive from ElementCollection
    * Consensus on having it derive from ElementCollection - no need for the additional "context" string
* Discussed the model changes based on our decision
* Question: Do we need a "Serialized XCollection" class
  * Sean and Gary and David agreed we needed the Serialized class to support some of the use cases 
  * No agreement or consensus of if we need it
* Options discussed:
    * Don't have a "Serialized XCollection"
    * Subclass of XCollection with additional property "Artifact" cardinality 1..* 
    * Separate class with 2 properties - XCollection and Artifact
      * If there was a need to serialize the information about the serialized XCollection in a separate serialization, it creates a problem when serializing - would require multiple "XCollections" in the same serialization re-introducing "where to we start?"
  * Only have a relationship between Artifact and XCollection
* No consensus or decision reached

## Decisions
* XCollection is a subclass of Bundle, not a subclass of Bundle

## Future topics
* Model definition of "Serialized XCollection"
* PR #500 proposes "serialized data" (Payload) structure: https://github.com/spdx/spdx-3-model/blob/44a32fb7099e105b2df09b7f7562de9ebc12ca4d/model/Core/Classes/Payload.md
containing the serialized element values and two properties used for compacting the serialized values: NamespaceMap and CreationInfoMap.  These properties are serialized as defined in the specification for each data format. This structure is a datatype, not an Element.
* Question: Do we move ExternalMap to the XCollection?
* Question: Do we want to change ExternalMap to reference the "Serialized XCollection" in addition to or in replacement of the location hint + verified using properties?
* Question: Should we move data license from creationInformation to XCollection? - this may be more of a model / tech call question
