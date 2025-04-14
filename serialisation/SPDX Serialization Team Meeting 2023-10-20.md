# SPDX Serialization Team Meeting 2023-10-20

## Attendees
* Sean Barnum
* David Kemp
* Nisha Kumar
* Gary O'Neall
* Jeff Schutt

## Agenda
* Review proposed diagrams
  * Sean's
  * David's
  * Gary's
  * Nisha's
* Decide on option 5 or option 1+4
1. It's any SPDX Artifact Element. It has to be a concrete subclass - File, Snippet, ByteStream <- Nisha
2. A specific concrete subclass of Artifact for this specific case <- Nisha
3. Subclass an Element with 2 properties: Artifact and SerializableCollection
4. A Relationship type that relates a SerializableCollection to Artifact <- Gary, Sean
5. A subclass of Element with property of type Element which is "stuff that is serialized" and LocationHint and VerifiedUsing. <- David: element values in payload contain everything logical, This class is orthogonal: contains only physical properties so it does not duplicate logical content.
        
## Notes
* Sean's diagram
  1. Elements is a bucket of content (whether it's in database or document form).
  2. ExternalMap referencing other elements and all this data is within a namespace.
  3. The serializable collection can now be transformed into physical content. If one of these files are available they can regenerate elements. But it doesn't verify the process that created them.
  4. If you want a verification, that gets created in step 4.
  5. Now a consumer can get all available data + the verification data and can regenerate the data.
  The intent is to communicate metadata about the process that created all the serializations that were created from the centralized source of elements.
* Jeff: what is step 2
  * Maybe there is a new version of the software, then a producer will mint new elements and reference existing elements.
  * Product team is tracking the software over time.
  * What is the "crafting" mechanism? Sean: like rdf data; Gary: or in-memory data
  * Nisha: what about software analyzers?
    * There is a step0 for analysis, then there is a step 1 which creates the elements and step2 will assemble the elements into a SerializableCollection.
  * David: 
  * Sean proposed to rename NamespaceMap to PrefixMap
  * Jeff: is it required for step 4 to be done in the same environment? Sean: it doesn't have to be.
* David's diagram
  1. Step 0 results in information about the elements + rootElement + we know what the NamespaceMap is
  2. These components can be directly serialized.
  * Gary: what if the native serialization doesn't have a rootElement? David: for JSON for example you will have to define a property called "rootElement".
  * David: we need to have a "closed Artifact class".
  * Gary: if the definition of "Artifact" is closed, would Artifact work? David: yes. You cannot have an Artifact element that doesn't have elements that are not defined in relationships. You cannot append relationships later.
* General discussion:
    * Jeff: rootElement vs NamespaceMap; for example headers vs value. metadata about the metadata vs metadata about the software. Are these about the metadata or content?
    * David: Content occurs 1ce per doc/bytes.
    * Jeff: doesn't that mean, it should be at the top? David: yes, it's the first thing to look at.
    * Nisha: SerializableCollection in the first diagram looks like "Payload" in the second diagram (with NamespaceMap, rootElement, and elements).
    * Gary: to know where to start in rdf there would be a type to hold the "where to start" property. What is the name of this type i.e. Class?
* Gary's diagram:
    * Specifically looking at difference between XML and JSON-LD. JSON-LD requires a property called "rootElement" which is supported in XML as part of the native serialization. XML has a tree structure, so we can find the root.
* Jeff: concerned about the end user consuming a document
* Gary: proposed is Artifact has a relationship to a class which is has an immutable list of elements
* David: the physical document Element needs to be able to convey what is in the payload.
* Gary: Artifact has a hash and is immutable. 
David Notes
PhysicalDocument serialization adds two elements to the model
It does not change or remove anything from X-Collection / SerializableCollection
* A closed collection's contents are defined by properties, and are immutable
* An open collection's contents are defined by relationships, and can be added to at any time
* SPDX decided to model Package as an open collection, subclass of Artifact
* Actual serialized data in XML or JSON-LD formats is immutable, modeled as a closed collection
PhysicalDocument serialization fully supports all requirements in Sean's table
