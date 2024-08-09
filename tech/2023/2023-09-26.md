# SPDX TECH Team Meeting 2023-09-26

## Attendees (9)
* Rob Craig
* Adrian Diglio
* Peter Monks
* Maxmillian Huber
* Nisha Kumar
* Rose Judge
* Andrew Reiter
* Marc-Etienne Vargenau
* Joshua Watt 

## Agenda
* UPDATE—https://github.com/spdx/spdx-3-model/issues/470
* William to complete the update on the documentation
* Group to review/comment on pull 490/491
* Review and prioritize open issues | identify those blocking progress on spec | close those identified items: https://github.com/spdx/spdx-3-model/issues?q=is%3Aopen+is%3Aissue+milestone%3A3.0-rc2+label%3Aserialization
* Serialization Update - Nisha

## Notes
* Serialization Update:
    * Decision #1 for JSON-LD: Use a type to identify where to start. If you're parsing JSON-LD then you look for the key named type.
    *  Decision #2: We need a class - currently calling it "Serializable Collection" but the name of the class is TBD. The class is a representation of a serialization. The class that defines if you are goign to serialize this data then you need to create an instance of a serializable collection. Should have at least two properties: 1) Root Elements: regular collection and, 2) the elements, which are included in any serialization.
    * More may come in the future. This is completely independent from all the namespace disussions and its not clear how these namespaces work with this proposal.
    * Some confusion still.
    * Current status: Encode "intent", "where to start", and "what this document contains" but the solution is still in discussion.
    * Namespaces are still under discussion
    * Serialization is the biggest hurdle for 3.0 right now.
    
* https://github.com/spdx/spdx-3-model/issues/495
  * Still a problem that we use RootElements to describe intent. This is a technical property that must point to all roots of the tree that is serialized, which can be used to traverse the edges of the graph.
  * This is a model issue that needs to be discussed in the next tech call once more folks are present to discuss.
  * Max and Nisha will followup in smaller setting to align 

## Decisions
*

## Action Items
*

## Next SPDX Tech Team Meeting 2023-10-03
