# SPDX Serialization Meeting 2023-09-21

## Attendees
* Gary O'Neall
* Max Huber
* Nisha Kumar
* David Kemp
* Sean Barnum

## Agenda
* Issue 478 - where do we start in JSON-LD: https://github.com/spdx/spdx-3-model/issues/478

## Minutes
* There are multiple SBOMs in a blob. A consumer would not know which blob to start with
* Which "start"? Gary: understanding start not parsing start. Eg: what is this bundle of data talking about
* Collective decision on a proposed solution: we were looking at it from a JSON perspective. If the whole thing was wrapped in a single Element. If there were more Elements we could use ElementCollection which has the "rootElement" property. However, single Element doesn't work in RDF.
* There was a "type" approach: Use a different class to capture this type of collection that indicates it's an outer wrapper.
* If it's a flat list, the consumer can re-serialize them as they want. However, if it is some graph, the consumer will have to preserve the graph.
* Alternative to Class, we could use a property. Sean: if it's about "understanding" it should be defined in the model. David agrees. 
* If something is in your mind and you write it down, but don't publish it...but if you edit it later, that is a different thing.
* Licensing is a distraction. Table it(?). 
* Difference between _intent_ to serialize and _actual_ serialized data. Deserializing means getting the same elements that the producer intends to communicate. Once the X collection is "minted" nothing can change from that point on.
* Let's call X collection "SerializableElementCollection". There can be only 1 of this in a blob of data. This will be a subclass of "Element" and have an Id. If there is just 1 SBOM then there is no need to use this.
* Rule: if you have a root element you have to put it in a SerializableElementCollection else don't
* Problem with subclassing is that the elements would have to be listed twice. How about "SerializableElement" where we have a root element that points to the collection and then have the actual list of elements somewhere else.
Three use cases:
    - multiple collections (Sboms in other Sboms)
    - single collection (one Sbom)
    - no collection (Licenses or Agents serialized together)
Max and Dave - don't need SerializableCollection wrapper for single collection or no collection case.
* Decision: 
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
* Update the tech team on the decisions
* Apply this to Nisha's examples and simple examples: https://github.com/spdx/spdx-3-serialization-prototype-playground/blob/main/implementations/4/acme_alpine_combined.json
  * Also the original JSON-LD: https://github.com/spdx/spdx-3-model/blob/main/serialization/json_ld/examples/converted_from_spdx_2.json
* Look at this solution across other solutions (namespace solution, data license solution)
* Discuss implication on other serializations
