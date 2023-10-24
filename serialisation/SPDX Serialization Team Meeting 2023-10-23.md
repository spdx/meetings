# SPDX Serialization Team Meeting 2023-10-23

## Attendees
* Sean Barnum
* David Kemp
* Nisha Kumar
* Gary O'Neall
* Jeff Schutt

## Agenda
* Conintinue discussion model
* Decide on option 5 or option 1+4
1. It's any SPDX Artifact Element. It has to be a concrete subclass - File, Snippet, ByteStream <- Nisha
2. A specific concrete subclass of Artifact for this specific case <- Nisha
3. Subclass an Element with 2 properties: Artifact and SerializableCollection
4. A Relationship type that relates a SerializableCollection to Artifact <- Gary, Sean
5. A subclass of Element with property of type Element which is "stuff that is serialized" and LocationHint and VerifiedUsing. <- David: element values in payload contain everything logical, This class is orthogonal: contains only physical properties so it does not duplicate logical content.
        
## Notes

* Sean's proposal:
    * In SerializableCollection we have property import which is of type ExternalMap which has property "definingArtifact" which is of type "Artifact". Here definingArtifact can be another SPDX SBOM.
    * Jeff: the properties on ExternalMap are not specific enough to indicate that you are using it to link to SPDX documents. Is there another use case?
    * David: alpine references 10 elements from "openssl", each entry in ExternalMap will have descriptions for each of these definingDocument/definingArtifact
    * Summary of issues:
        1. number of entries on the externalMap (Sean: should be one for each defining document and externally referenced document; could be a large list if a large set of Elements)
        2. When do we need a payload to include SerializableCollection (Sean: if you don't do it you have no context of what you are getting)
        3. Only one SerializableCollection can be created in a serialized blob of SPDX data; represents the metadata (header properties) in that payload; you can reference others by their SPDX ID but can't define in that blob
        4. Does the relationship have value?
        5. If you don't include SerialiableCollection it may be impractical to get all the information you want (it will be lost/context won't be provided), in practice SerializeableCollection must be in every SBOM
Rough Consensus: agree this could work provided it's optional
* David's proposal:
     * "PhysicalDocument" is  the representation of the physical bytes. There is no need to include "SerializableCollection". 
     * "PhysicalDocument" has type "documentInfo" which has the document header information. The "documentinfo" is in the bytes and is also in the "PhysicalDocument" in logical form.
     * To know the SPDXID of all elements in a PhysicalDocument needs to find all the SPDXIDs of externally referenced (?)
    
