# Namespace Discussion 2023-09-18

## Attendees
* Gary O'Neall
* David Kemp
* Sean Barnum
* Bob 


# Notes
* Sean's PR is solution A - SerializableCollection
* Gary's PR is solution B - SpdxDocument (or SerializedCollection)
* Bob says producer always has to follow his own intent
* David agrees if they duplicate then both must match
* How do you capture the original intent of the namespace to be used?
  * do we need to express the namespace 2x in a document to clarify originator namespace vs ? namespace
  * option 1 - originator prefix encoding MUST be expressed by the SPDX content originator 
  * option 2 - namespace prefix can be presumed to be extracted from the specific serialization format's namespace rules
* Gary desires to preserve original namespaces from the SPDX serialized content (v2 SpdxDocument) received
* What happens if namespacemap is different between the document and the JSON-LD context?
  * reject the duplicate data, chose which one?
* Which namespace do we use?
  * only original producer is the one I received the SPDX serialized content from?
* Do we need to have the provenance of the namespacemap used for SPDX metadata (not software artifact metadata)?
* Does namespace map in the original producer's serialized SPDX data (whether Alpine-created or Cisco-created about Alpine software) support provenance?  Yes, because it's free.
* David: Solution B - SpdxDocument element contains "downloadLocation" of the producer's original serialized SBOM, the location from which the consumer/producer obtained the serialized data.  If SpdxDocument also includes verifiedBy, integrity can also be enforced.

* TODO: team needs to continue working on the name of this x collection

**Team agreed on:**
* org has flexibility to namespace however they want
* scope: the namespace prefix is significant to this collection of elements
* agree to move forward with solution B for SPDX 3.0. Team accepts that if we need to accommodate aspects of solution A it may be a breaking change that would require changes in the next major spec version; will use testing of namespacemaps in version 3 to learn more
* Solution B = X collection is metadata about a serialized byte sequence created by original producer




* externalmap, as a property of ElementCollection, is scoped to external SPDX elements
* if Acme Application SBOM references Alpine SBOM, does the producer need to reference the alpine collection via externalmap?
  * Yes if it references the alpine SBOM and includes the original SPDX IDs it MUST use externalMap
  * Provided the creator of Acme Application mints new elements with new SPDX IDs, the use of externalMap is not necessary
- proposal: move `import: ExternalMap` to the `SpdxDocument`
- proposal: include locationHint and verifiedUsing properties (from ExternalMap) in SpdxDocument.  
- proposal: rename ExternalMap to ExternalSPDXMap or ExternalElementMap
