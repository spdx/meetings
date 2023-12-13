# SPDX Tech Meeting 2023-09-05

## Attendees
* Bob Martin
* Karsten Klein
* Gary O'Neall
* David Edelsohn
* Jennie
* David Kemp
* Rose Judge
* Maxmillian Huber
* Kate Stewart
* Rob Craig
* Nisha Kumar
* Jeff Schutt
* Joshua Watt
* Jim Hutchison
* Dick Brooks
* Brandon Lum

## Agenda
Documentation Status (William)
Namespace Map Serialization (Gary/Sean/William/David/Max)
How to Specify Mandatory Relationships (Sean/Alexios/Gary/Max)
Profiles - Interpretations (Jeff/Gary) back to the larger group
Model Diagram - master to be updated with added profiles

## Notes
Namespace Map
Recap of last week - agreement on use cases - additional details on the round-trip use case
Wrapping up the serialization meeting - 2 proposals to compare and decide
Sean's Proposal: 
https://github.com/spdx/spdx-3-model/pull/490
Max's Proposal: (per discussion, can be considered optional for some)
Profile properties - do we want to apply this to agent?    (pending to 3.1 assuming non breaking change)
Who creates it, states intent in conformance profile.   Do we want to describe what the agent can handle.
Can we have a namespace different from the one outside a collection?
Is element talking about serialized data or potential serialized data?   If you haven't serialized it yet, can you capture the property of namespace. ?

## Decisions
* Tentative Sean -  Profile properties from Creation Info to Element Collections.
* remove profile property from CreationInfo.md
* add profileConformance and profileNamespace (existing definition of profile.md) optional properties to (ElementCollection, ...)
* Gary to do write up;  Jeff to review.

* The "X collection" is the outershell where the namespace map resides.
* The namespace map is only relevant to serializations. 
* All of the solutions involve the model (for supporting the namespace map)

* Tentative - Sean - The "X collection" is an outer shell, representing a serialization of SPDX data. 

## Action Items
* Gary to send out to spdx-tech - additional meeting with tomorrow at noon EDT - Gary, David, Max, Jeff, Sean tomorrow to resolve namespace.

## Next SPDX Tech Team Meeting 2023-09-12

=====================================================================
