# SPDX Serialization Meeting 2023-10-5 and 2023-10-16

## Attendees
* Gary O'Neall
* Max Huber (attended 1st and part of second meeting)
* Nisha Kumar
* David Kemp
* Sean Barnum
* Jeff Schutt

## Agenda
* Review decisions from last meeting and approve minutes
* Feedback and proposal from license discussion with legal team
* Work through remaining questions in David's email and the follow-up from last meeting
 Model definition of "Serialized XCollection"
* PR #500 proposes "serialized data" (Payload) structure: https://github.com/spdx/spdx-3-model/blob/44a32fb7099e105b2df09b7f7562de9ebc12ca4d/model/Core/Classes/Payload.md
containing the serialized element values and two properties used for compacting the serialized values: NamespaceMap and CreationInfoMap.  These properties are serialized as defined in the specification for each data format. This structure is a datatype, not an Element.
* Question: Do we move ExternalMap to the XCollection?
* Question: Do we want to change ExternalMap to reference the "Serialized XCollection" in addition to or in replacement of the location hint + verified using properties?
* Question: Should we move data license from creationInformation to XCollection? - this may be more of a model / tech call question
* Follow up from Oct 11 meeting:
    * David's input to the No 5 solution:
        - bytes in XML or JSON format: "payload"
        - Element that is metadat about payload = "SerializedElements"
        - SerializedElements has element, verifiedUsing, and locationHint properties
        
        SerializedElements is subclass of 1) Element, 2) ElementCollection, or 3) Artifact
        David: Agree that SerializedElements can be subclass of Artifact with "element" property to avoid multiple inheritance with ElementCollection (may also include "rootElement" property for where to start use case)
        
        Sbom, Package, File:
            payload1 has Sbom that references Package, File + SerializedElements of payload2
            payload2 has Packge, File
        
        v2 = Document
        v3 SerializedElements =  PhysicalDocument
        v3 SerializableCollection = LogicalDocument


## Notes
* Review minutes - Agreed to merge
* Follow up from last call
  * David's structure for discussion proposed in email thread. Max will read the email thread and reply as needed.
  * Jeff proposed recording votes from each person and Max can record his agreement/disagreement after the meeting. Agreed if there is general consensus to make a tentative decision and revisit objections from max if they include an alternate proposal.
  * SerializedCollection pushed to 3.1?
* Feedback from legal team on DataLicense: It is required in SerializableCollection/XCollection but NOT in Element. It would add more complexity in interpreting it.
  * Sean: this is contrary to experience
  * Gary: need someone with a law degree to represent why
  * David: from IC perspective it seems like an element and a relationship to an SBOM. Security classification on an element (paragraph/portion marking) vs Security classification on the overall document.
  * Jeff: with respect to copyright the feedback makes sense. Must provide a more accurate definition of DataLicense.
  * Gary: proposal to add an optional license for "AnyLicense" in SerializableCollection/XCollection
  * Current proposal: Change DataLicense from being in Element to being in SerializableCollection/XCollection. The semantic intent is to apply the license to the serialized form of the collection.
  * Jeff: would rather wait on the legal team for clarification. Gary: would like to agree on syntax and legal team can give input on semantics.
* David's email:
    * ExternalMap uses the word "Document". This is data that can be cryptographically verified.
    * Sean: "Document" is a historical term.
    * David: is it always "Document"? Sean: yes, it represents a sequence of bytes.
    * Jeff: what is missing? Payload -> id -> mapped in ExternalMap?
    * Sean: 1. Should we still call it DefiningDocument 2. It's an anyURI, but should it be constrained it some more?
    * David: two things 1. bytes 2. SerializedElements pointing to bytes.
    * Sean: the link to the payload is the LocationHint. Eg: received a payload which has content that was defined in the payload, but is also likely to have references to content inside another payload. Eg2: payload has content that describes a container that has a reference to a layer and the layer is defined outside the content. ExternalMap will have an entry for openssl.
    * LocationHint: the location of element or payload or anything. DefiningDocument is an SPDXID.
    * David: a payload has 42 elements, the 42 elements reference 100 more. Sean: the 100 external things can come from 10 different places. David: one way to implement this is using ExternalMap but another way to implement to use SerializedElements.
    * Jeff: if one used LocationHint and used URI, should we also use DefiningDocument. Sean: not necessarily.
    * Decision: there is something in the model that represents "SerializedElements" that covers these use cases. (yes - PR #500)
    * Sean: Should "DefiningDocument" be "SerializedCollection" or "File"?
    * David: LocationHint is a URL (not anyURI) and definingDocument type is an SPDX ID?
    * Sean: should DefiningDocument type be a serialized collection or an Artifact?
    * Gary: is DefiningDocument an "artifact" or is it something else?
    * Gary: what is the type of definingDocument? (1) an Artifact (2) yet-to-be-defined class representing serialized SPDX Elements
    * David: Proposal for "SerializedDocument" element.  Not a subclass of Artifact, not multiple inheritance.
Just a subclass of Element, plus verifiedUsing and locationHint: https://github.com/spdx/spdx-3-model/blob/44a32fb7099e105b2df09b7f7562de9ebc12ca4d/model/Core/Classes/SpdxDocument.md (change name from SpdxDocument to SerializedElements)
    * Sean: concern that SPDX v2.3 SPDXDocument represents both the sequence of bytes of a serialization or the physical form of the data (e.g., a recipe card, e.g., serialized SPDX 3 Artifact Element(s)) and represents the description/characterization of the SPDX content contained in that sequence of bytes or the logical form of the data (e.g., a recipe, serializableCollection)?
    * General consensus that this separation must be made in SPDX 3
    * General consensus that the model must be able to specify these two distinctions: physical vs logical
    * 3 representations proposed: 
        1. Byte Sequence (physical form of data, a payload), defined in the serialization specification
        2. SerializedCollection (logical element that describes physical data, content), defined in the model
        3. SerializableCollection (logical element that describes a logical collection, semantically correct), defined in the model as XCollection
    * Gary: using SerializableCollection/XCollection to represent the logical data in the model, regardless of whether it is always, sometimes, or never serialized
    * Gary: Does SerializeableCollection mean the same thing as the logical form of the SPDX v2 SPDXDocument?
      * General consensus that this is true
    * David: there is a physical form of the SPDX v2 Document. What is that? A serializedCollection Element (representation #2 above) describes that physical form
    * Sean: Should that physical form represented in the model be an Artifact or a subclass of Artifact?
    * Gary: options:
        1. It's any SPDX Artifact Element. It has to be a concrete subclass - File, Snippet, ByteStream <- Nisha
        2. A specific concrete subclass of Artifact for this specific case <- Nisha
        3. Subclass an Element with 2 properties: Artifact and SerializableCollection
        4. A Relationship type that relates a SerializableCollection to Artifact <- Gary, Sean
        5. A subclass of Element with property of type Element which is "stuff that is serialized" and LocationHint and VerifiedUsing. <- David: element values in payload contain everything logical, This class is orthogonal: contains only physical properties so it does not duplicate logical content.
        6. A subclass of SerializableCollection/XCollection
    * Sean: 1, 2,3 & 4 are all focused on how to represent the serialization physical data. 1 and 2 - representation is a type of Artifact, 5 and 6: it's a non-Artifact class that represents an Element. An "Artifact" is defined as “An artifact is a distinct article or unit within the digital domain, such as an electronic file, a software package, a device or an element of data.”. As such it is an article in the digital domain. If we use a non-Artifact Element we are duplicating semantics already defined in Artifact. This makes 5 & 6 not valid choices. We also need to associate logical and physical together, 3 and 4 attempt to do that. 4 is the clearer and SPDC standard way to connect SerializableCollection and Artifact. My opinion is either 1 or 2 are valid choices for representing the serialization physical data. Gary expressed a preference for 1 given some other use cases. I think this makes sense and 1 would be preferable to 2. Overall, I think the best choice is 4 where the Artifact side of the relationship is 1.
    * General consensus that 6 isn't an option
    * Gary: important to note that there's a need to express three things: the logical content, the physical data, and a correlation between them
    * Also, what is the range of the property in the ExternalMap (?)
    * And do we need a property on the concluded classs/relationship that is an enum of the serialization formats (XML, JSON, YAML, etc.)?
   * Gary: would like to support byte stream. It could be the subclass of Artifact. If there is a specialized class, it may not support the byte stream. Similarly, there could be a future need to burn the SPDX data into hardware; suggests 2 isn't a viable option
   * Nisha: wants to separate SPDX artifact from any other type of artifact
   * Gary: in SPDX 2 there was a filetype for SPDXDocument; there are MIME types for SPDX (both SPDX JSON and SPDX Tag-Value)
   * Nisha: if it's a byte stream, how do I know it's SPDX data?
   * Gary: a property to indicate it is likely needed, perhaps a bytestream subclass of artifact and we reuse the mime-types. add the same property as is already in the File Element (contentType: MediaType)
   * General consensus: 2 isn't an option
   * Interim Decision: for the physical data form of the SPDX artifact, using 1 is best given that there is a property that will codify if the content is SPDX content
   * Now how to correlate the SerializeableCollection and the physical data (1)?
     * Gary: option (3) was his proposal, doesn't believe it is as good option as (4)
     * Interim Decision: use (4) a relationship type 
  * ExternalMap has property definingDocument and property verifiedUsing that is against the definingDocument
    * does the definingDocument URI point towards the relationship or the artifact?
    * it points to the artifact
  * what is the from and the to in the relationship?
    * from: artifacts to: serializeableCollection <- pros: none cons: requires separate relationship for every artifact
    * from: serializableCollection to: artifact(s) <- pros: only requires 1 relationship for the serializeableCollection
    * what if we don't constrain the relationship? if add a new `relationshipType: hasSerialization` wouldn't be able to let it be either way
    * example: from: serializableCollection hasSerialization to: artifact
    * David: still have a viewpoint on the physical data but agree with the logical model. Sean: SerializableCollection/XCollection is just "data to be serialized". David: in addition the Serialization data format is not dependent on SerializableCollection/XCollection. 3rd decision covers this.
    * David: Given we ignore SerializableCollection/XCollection, we can use the binding and schemas to communicate everything in the model except for this element. Then it should still work.
    * Sean: the separation covers layers of value beyond.
    * Gary: this information can be provided out of band of the actual serialization.
    * Sean: yes, but standardization is useful for machine readability.
    * David: we need to have a "where to start" and "verifiedBy" and "locationHint", this considers "in-band". Proposal 5 is an alternative if SerializableCollection is not defined.
    * Sean: if we received a file with a bunch of elements, how would you isolate a particular element?
    * David: "physical form" -> "payload",  SerializedElement -> class that has "elementValue", "locationHint" and "verifiedUsing" properties.
    * Sean: is SerializedElement is an Element in the model that represents the physical data. Should it also contain metadata that is con (?)
    * Sean: if we allow for the optional merging of the physical and logical form that will create multiple elements.
    * David: but the "SerializedCollection" will support this.
    * David: SerializedElement replaces ExternalMap. Sean: they are not the same thing.
    * Gary: would "SerializedElement" be defined as a model class? David: yes.
    * David: on what is external and what's not, if there is a payload with one element SBOM and has 2 ids and those are in a different payload then SerializedElements of payload2 are included in payload1. Sean: how to provide info about where payload2 is and where to find it.
    * Gary: seems like SerializableCollection covers the all the requirements except for the artifact. So we can combine this and Artifact.
    * David: "SerializedCollection" simplifies the process and doesn't prevent you from doing the above. This is better.
    * Went through alpine:latest container example. Still need resolution on whether to use option 1 & 4 or option 5

From Gary's notepad on comparing option 5 and option 1 & 4

Example:

OpenSSL is serialized in payload A
alpine:latest is serialized in payload B


Option 5 Acme Example:
* payload A just contains the OpenSSL metadata
* payload B has 2+ elements:
  * alpine metadata
  * Contains relationship between Alpine:latest and OpenSSL
  * SerializedElements which contains the location, verification, and elements serialized in payload Acme
  
Option 1 & 4:
* Payload A just contains OpenSSL metadata
* Payload B contains the following:
  * Alpine:latest metadata - "Software Artifiact of type Package"
  * Contains relationship between Alpine:latest and OpenSSL
  * PayloadB has a "SerializableCollection" metadata included in the payload b serialization that includes an external map for the reference to payloadA
  * Artifact ID for payloadA - can be interneral or external - in the external map
  * VerifiedUsing data for the Artifact for payloadA in the external map

* Optionally:
  * "SerializableCollection"/"XCollection" for paylod A
  * Artifact for payload A with the mimetype for SPDX
  * Relationship between Artifact and "SerializedCollection"


Notes/Conclusion:
- Any external reference requires a "SerializableCollection" / "XCollection" to be created

## Decisions
* XCollection is a subclass of ElementCollection, NOT a subclass of Bundle
* SPDX v2 Document should be separated into "physical" and "logical" form in SPDX 3
* XCollection/SerializableCollection represents the "logical" form

## Future topics
* Start with Sean's diagram sent in email
* PR #500 proposes "serialized data" (Payload) structure: https://github.com/spdx/spdx-3-model/blob/44a32fb7099e105b2df09b7f7562de9ebc12ca4d/model/Core/Classes/Payload.md
containing the serialized element values and two properties used for compacting the serialized values: NamespaceMap and CreationInfoMap.  These properties are serialized as defined in the specification for each data format. This structure is a datatype, not an Element.
* Question: Do we move ExternalMap to the XCollection?
* Question: Do we want to change ExternalMap to reference the "Serialized XCollection" in addition to or in replacement of the location hint + verified using properties?
* Question: Should we move data license from creationInformation to XCollection? - this may be more of a model / tech call question
