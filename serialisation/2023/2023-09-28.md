# SPDX Serialization Meeting 2023-09-28

## Attendees
* Gary O'Neall
* Max Huber
* Nisha Kumar
* David Kemp
* Sean Barnum

## Agenda
* Update the tech team on the decisions
* Apply this to Nisha's examples and simple examples: https://github.com/spdx/spdx-3-serialization-prototype-playground/blob/main/implementations/4/acme_alpine_combined.json
  * Also the original JSON-LD: https://github.com/spdx/spdx-3-model/blob/main/serialization/json_ld/examples/converted_from_spdx_2.json
* Look at this solution across other solutions (namespace solution, data license solution)
* Discuss implication on other serializations

## Minutes
* Discussion on the duplication of the element ID list
  * 2 proposals:
      * serialize the "SerializableCollection" list of element IDs
      * IF the serializable format natively supports the closed element list itself (e.g. the @graph in JSON-LD), we would not include the element list
  * Advantage of the serlializing the element list is that you could use it to verify the serialized elements - similar to a packing list in a box of content or a manifest
  * Advantage of not serializing the list is brevity and not duplicating information - note: if the information is used for verification it really isn't duplicated
* Decision - if we did always serialize the element list, it would be primarily used for verification and the the native serialization contains is what is really contained in the serialization (as captured in the "SerializedCollection" which represents SPDX data which has already been serialized) - we would document that the element list is provided for verification purposes and not to be confused with the list of actual elements serialized. The "SerializableCollection" and "SerializedCollection" classes work in concert to express what 'should' but in the serialized content and what 'is' in the serialized content and are machine comparable to provide clear verifiation.

## Decision from last time:
    * For JSON-LD we will use a type to identify where to start
    * We will have a class name TDB "SerializableCollection" which contains at least 2 properties
      * rootElements
      * elements - the elements are what are actually to be included in any serialization
      * similar to a Manifest
  * We will serialize the TDB "SerializeableCollection" in JSON LD
  * When deserializing
    * If we find a "SerializableCollection" TDB Name, that tells us what the JSON-LD file is about
    * else  all elements are treated as being root elements
    * The consumer may choose to retain the "SerializableCollection" TBD Name or not
* Note: There may be different solutions for non-JSON-LD serialization

## Next Steps
