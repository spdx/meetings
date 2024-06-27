# SPDX Serialization Team Meeting 2023-07-20

## Agenda

## Attendees
* Nisha Kumar
* Mark Gisi
* Armin Tanzer
* Maximillian Huber
* David Kemp
* Gary O'Neall
* Jeff Schutt
* Jonathon Gardner


### Regrets
- Alexios Zavras (got pulled into another call)

## Notes
* discussion on if and when to support various serialization formats
* general agreement to support mulitple formats at some point in the future
* decision made to support JSON-LD for 3.0, the work has already been done
* question on whether to support only 1 serialization (beyond JSON-LD) for 3.0 or more than one?
* need the serialization chosen to be friendly to developers & implementers (concern about JSON-LD)
* David: current context simplifies the JSON-LD to JSON compatibility but JSON  does not support @context and @graph which is what developers are looking for (validate using JSON Schema) (+1 Jeff - maybe we support both JSON-LD and JSON)
* Gary: from the current status, JSON-LD is done, so we can move on to JSON or "lawyer friendly"
* Consensus: JSON-LD and JSON with support for @context and @graph
* Topic: target audience then talk about where we focus
* there are multiple audiences that would prefer different serialization formats for SPDX
* the most important community to focus on after JSON-LD is the developer community in general
* the developer community has a certain set of requirements that we should consider when choosing a format
* developer criteria to consider: 
  * implied that they prefer JSON (based on prior discussions)
  * also should be validated from a JSON schema all by itself (w/o a context file)
  * easy to use as part of a library you incorporate into your code base
  * how much extra code is needed to write beyond what's provided in standard tools, e.g., how much logic is required for parsing, desire not much logic and custom parsing required on top (may be unavoidable); don't want to introduce additional JSON complexities in order to support JSON-LD
* that it can be validated
* developer (human) readability
* lossless
* SPDX 3.0 in the serialiation format supports a real-world example
* Alternatives that could support the above criteria
    * will use JSON-LD as a benchmark in case it supports the criteria better
    * David has proposed a JSON format, and Thomas has suggested a JSON framework
    * One JSON-LD proposal: https://github.com/spdx/spdx-3-model/issues/138
    * Jeff, Nisha, David: would like to use real world examples
    * Rose and Jeff created a drawio diagram with real examples in security team meetings/examples folder: https://github.com/spdx/meetings/tree/main/security
    * JSON blobs supporting the security profile that correspond to the nodes in the drawio diagram are embedded in the description of the associated classes in the SPDX 3.0 model repo here https://github.com/spdx/spdx-3-model/tree/main/model/Security/Classes
