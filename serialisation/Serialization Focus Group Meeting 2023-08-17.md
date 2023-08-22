# SPDX Serialization Focus Group Meeting 2023-08-17

## Attendees
* Gary ONeall
* Nisha Kumar
* Sean Barnum
* David Kemp
* Armin Tänzer
* Jeff Shutt
* Maximilian Huber

## Agenda
* David to propose a JSON

## Notes

* Blank Notes in JSON
  * 
* Namespace Map
  * Different proposals
    * Go back to using namespace map in collection - Use a collection that only represents the outer layer - can not include another 
    * Max's proposal - deserialization profile https://github.com/spdx/spdx-3-model/pull/479/files
    * Add namespace map on SpdxDocument https://github.com/spdx/spdx-3-model/pull/403
* We will not decide on the name (SpdxDocument, Payload, etc.) until we finish defining what it is
* Max raised a concern on complexity on outer layer approach
* Discussion that Sean and Gary's proposal are now similar if we remove the name of the class
  * Gary's proposal defines namespace map as the "initial namespace map"
  * Sean's proposal defines namespace map as a "hint" which can (but not require to) be used
* Related issue of data license which may apply to a serialized form
* Question on if we use "file" to represent the serialized form
  * Issue of creating a file which contains the checksum of the file - recursive issue
* Issue of creating everything in one shot vs pulling in elements created with different namespace
* David: Producer centric since the producer is producing the BOM with the namespace map
* Jeff: Producer and consumer are equally equivalent 
* Gary and Sean's proposal - very similar, difference in use of File and rules for if/when you embed one of these classes inside the other
* Max's proposal - three uses:
    1. Producer creates an "X" element (SpdxDocument, Payload, File) to facilitate generating a payload but doesn't include it in payload
    2. Producer creates "X" element describing payload and does include it in payload
    3. Consumer parses a payload and generates an X element to capture some information from it in the element graph, to be used when consumer produces new payloads.
* Idea - can use the same model proposed by Gary and Sean with rules proposed by Max for how it is used in serialization / deserialization
* Difference between Max/David proposal and Gary/Sean proposal is whether the namespace map is serialized as a class or serialized in a serialization specific approach
* Next step: Continue discussion on Tuesday's tech call
  * Decide if we're going to serialize the class  (resove the difference in the bullet above)
  * Decide on the properties and semantics of the class
  * Do NOT decide on the naming - we'll save that for a follow-up call
