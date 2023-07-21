# SPDX extra call on JSON-LD Creation Info Serialization 2023-07-21

## Attendees
* Alexios Zavras
* Andrew Reiter
* Gary O'Neall
* Hutch
* Jeff Schutt
* Kate Stewart
* Maximilian Huber
* Nisha Kumar
* Norio Kobota
* Rob Craig
* Rose Judge
* Sean Barnum
* Takashi Ninjouji

## Notes

three examples of different approaches
in https://github.com/spdx/spdx-3-serialization-prototype-playground/pull/3

* "full"
  - essentially Elements are on top-level graph, other info is embedded
  - uses external @context to produce something human-readable (and looking like JSON) 
  - every object has to have a unique id (currently missing)

* "with-blank"
  - CreationInfo (multiple ones) are as blank nodes, other Elements refer to these
  - each creationInfo has unique id, but on document-level, not globally-unique
    - therefore they cannot be reused as-is
    - but this is a serialization covention, all info must be created 

## Decisions
*

## Action Items
*
