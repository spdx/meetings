# SPDX Tech Team Meeting 2023-08-22
 
## Attendees
* Adolfo Garcia Veytia
* Andrew R. Reiter
* Armin Tänzer
* Bob Martin
* Brandon Lum
* David Edelsohn
* David Kemp
* Jeff Schutt
* Jennie Kauffmann
* Joshua Watt
* Matt Rutkowski
* Maximilian Huber
* Peter Monks
* Rob Craig
* Rose Judge
* Sean Barnum
* Thomas Steenbergen
* William Bartholomew

## Agenda
* Recursive creation info in core - question - Rose + security team
* NOASSERTION on VersionInfo requires any doc changes? - Brandon
* Define NamespaceMap in model (https://github.com/spdx/spdx-3-model/issues/482)?

## Notes
* "Recursive creation info in core - question"
  * Security is working on some example and tries to fit it in JSONLD
  * The acme organization can create itsel, so the creator could contain the ID of the element
  * see also: https://github.com/spdx/spdx-3-model/issues/123
  * Issue 123 involves conversion from 2.3 to 3, which has the added complication that creators/annotators are just strings (e.g. name with no SPDXRef) in 2.3, but Actors are elements in 3.
* "NOASSERTION on VersionInfo requires any doc changes?"
  * noassertion was discussed in https://github.com/spdx/spdx-3-model/pull/456, https://github.com/spdx/spdx-3-model/issues/204 and https://github.com/spdx/spdx-3-model/issues/76, https://github.com/spdx/spdx-3-model/issues/71
* "Define NamespaceMap in model"
  *  see https://github.com/spdx/spdx-3-model/issues/482
  * there are problems
  * Sean: the problem is just the layering
  * ... lenthy discussions (Max, Sean, William, David) with limited notes taken
* Sean referenced having talked about prefixes in the SPDX Serialization Meeting—what would need to be improved are changes to the model which can eliminate the layering. 
* Proposals on the table can be implemented easily by placing them at the outer layer. 
* How to handle the SPDX Document class versus Sbomb?  Avoiding layering is the best solution. If you're merging 2 things, you would have to decide how you reconcile any conflicts in prefixes. That avoids that conflict. * A single element, a single collection, a single document, would implement the namespace map; you wouldn't have to do anything extra.
* 2 different collections in one serialization represented on the diagram as a payload. It's not part of the logical model. 
* More time is need to experiment and demonstrate that this approach works. Deferred it so long as it's just a hint and as long as serializations. So long as it’s just a hint—okay with that; but it belongs only in serialization.
* Gary's suggestions to put [it] on documents to ensure that it could only be used in the serialization was referenced. 
* Duplication seems to be the main motivation to have the namespace map. Do we just recommend compression? Compression is a separate issue, but you can always add compression too.
* 2 different directions—consumption of content and production of content.
* The initial problem: You don't know where the namespace begins and where the ID starts.
* William suggested documenting scenarios where we think this doesn't work, we can look at them and determine if there are reasonable solutions in those scenarios. If they aren't (reasonable solutions), then we go back and revisit the requirement. I think we need to try and solve the problematic scenarios before we say that we're going to go back to the original decision. Ask the people who are finding the problems to document what the problems are. So that [they] can be examined. This approach was agreed to.
* Sean proposed creating a scenario illustrating the problem and asked if people could help identify and document and give a simple example. Until we know exactly what the problems that are being raised are, like the layering one. Recommends working on this in the collaboration to document.
* William suggested that what is needed is scenarios that we think don't work so that we can look at those. We can collaborate on a solution. Bring it to the group. This scenario has a challenge, let's see if we can fix that. If we can't, then we step back and look at the requirements. Problematic scenarios: something concrete to test against.
  * https://github.com/spdx/spdx-3-model/pull/411/files
  * Thoughtfully-structured element IDs may facilitate defining meaningful prefixes
    - need scalable (to millions of elements) element ID examples
    - no public non-2.3 element ID examples have been identified
  * Considerations:
     - Shortening efficiency: prefixes scoped to a single document vs. prefixes scoped to multiple documents
     - Deconfliction of prefixes - are multiple JSON-LD serializations possible?

## Decisions
 * NamespaceMap, if included in the model, is a hint not binding on serializations

## Action Items
* Brandon Lum: we document what the meaning of NOASSERTION in the context of cardinality. The same way as a non existing relationship es equivalent to a relationship to NOASSERTION.
* Sean asked William for access to the repo. He was not able to do PR for writing up blank note decisions. Did not have permission to create a branch. William will investigate this.

## Next SPDX Tech Team Meeting 2023-08-29

=====================================================================
