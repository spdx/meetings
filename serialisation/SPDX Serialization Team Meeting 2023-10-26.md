# SPDX Serialization Team Meeting 2023-10-26

## Attendees
* Sean Barnum
* David Kemp
* Nisha Kumar
* Gary O'Neall
* Jeff Schutt

## Agenda
* Conintinue discussion model - starting with option 5
* Decide on option 5 or option 1+4
1. It's any SPDX Artifact Element. It has to be a concrete subclass - File, Snippet, ByteStream <- Nisha
2. A specific concrete subclass of Artifact for this specific case <- Nisha
3. Subclass an Element with 2 properties: Artifact and SerializableCollection
4. A Relationship type that relates a SerializableCollection to Artifact <- Gary, Sean
5. A subclass of Element with property of type Element which is "stuff that is serialized" and LocationHint and VerifiedUsing. <- David: element values in payload contain everything logical, This class is orthogonal: contains only physical properties so it does not duplicate logical content.
        
## Notes
* Discussed "Flow A" and "Flow B"
* Discussion on the differences between metadata properties in Flow A and Flow B - ID's are in FlowA 
  * General agreement that the ID can be useful
* Agreed that if ExternalMap is not part of SerializableCollection, the two flows are identical (enough)
* ExternalMap may require multipled downloads - required for validation
* Discussion on populating the ExternalMap - downloadLocation and Hash
* Discussed whether we needed to hash the document being created to include in the ExternalMap
* We will test the ExternalMap solution with the Tern implemenation to see if it is understandable and efficient
  * Compare the size and efficiency of ExternalMap vs 2.3 and the PhysicalDocument solutions
  * Gary will follow up with Nisha and Rose on ExternalMap vs. 2.3
  * David will take the results and mock up what the PhysicalDocument size / efficency

## Decisions
* OK to use "SerializableCollection" with the exception of ExternalMap

## Next Meeting
* What do we name the "SerializableCollection"
* Review ExternalMap efficiency (if time for Rose and Nisha)
* Review / create pull requests to implement the decisions so far
