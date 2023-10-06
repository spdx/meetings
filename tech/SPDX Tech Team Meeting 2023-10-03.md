# SPDX Tech Team Meeting 2023-10-03

## Attendees (13)
* Kate Stewart
* Gary O'Neall
* Peter Monks
* Sean Barnum
* Nisha Kumar
* Jeff Schutt
* Dick Brooks
* Rob Craig
* David Kemp
* Maxmilian Huber
* Bob Martin
* Joshua Watt
* David Edelsohn

## Agenda
* Update on documentation - William
* Update on relationships review - Kate
* Decide on serializing element lists: https://github.com/spdx/spdx-3-model/issues/505
  * Carryover from the serialization meeting Pull request: https://github.com/spdx/meetings/pull/486
  * Serialization group's significant progress
  * Key decisions and clarifications made
  * Lack of consensus on serializing collections aspect
  * Trade-off between manifest for verification and document brevity

## Notes
* Looking for examples of build profile in JSON-LD.   Nisha will work on PR for the playground.  Gary volunteering to review example when available. Gary: once 3.0 spec out use the SPDX examples repo and have one directory for each of the profiles to post a number of different examples for reference. Too early to do that now-serialization spec not solid.
* Relationship proposal to be reviewed next meeting
* No update from William re: documentation and partial update. 
* Dick provided https://www.federalregister.gov/documents/2023/10/03/2023-21328/federal-acquisition-regulation-cyber-threat-and-incident-reporting-and-information-sharing which is relevant for SBOM. 

* spdx-3-model/issue/505
* Decide on if we include the list of elements in addition to the native serialization of elemensts.
* Gary provided a synopsis of the outcomes of the Serialization team meeting:
  * Decisions were made to address the "where do we start" issue with SPD files.
  * The solution is called the X collection.
  * The X collection represents the serialization and solves the "where do you start" problem.
  * There will be only one X collection type in the file.
  * The X collection has a property called the root collections property, which indicates where to start.
  * Define X collection in the model—contains root elements and a list of elements for serialization
  * Serialization includes parts of X collection—Necessary for serializing root elements
  * Actual elements list is the list of file elements
  * Trade-off: Serialize entire X collection or only uncovered information
Gary refered to Proposal A (example)
  * Simple full specs class example—Json-LD file structure (Refer to example in 505)
  * Json-LD structure contains a "graph" with all different classes, each class listed separately in an array
  * Graph includes content of interest- one package and one file, X collection included
  * the root element is the what we really care about—it tells us where to start and then it has an extra array of elements.
  * IDs are exactly the same as the other IDs listed in the file with the exception of the collection itself
  * Second proposal- duplication is unnecessary unless it's for verification. Gary called out that the two examples shown only differ in the absence of an element graph.
  * Advantages and disadvantages captured from Serialization call- Gary drew attention to the decisiomn that the Serialization Team made, pointing out that the element list in the file is for verification, while the X collection list is only for verification purposes.
  * The model is identical for both examples. Serialization and deserialization of the information is what differs.
  * Verification use case is covered in use case one, but not in use case two.
   * "X" collection - serialize root, but its the list of the elements in the file itself.
  * Kate raised a concern that current properties on relationships may not effectively map to the signaling of known unknowns—need to keep an eye on this.
  * Gary: do we include a list of elements or not in the in the serialized form? Doesn't want to conflate this with the question of do we include the list of elements in the collection like a manifest.
   * Sean discussed use case of intent vs. what is present.
* Sean proposing 3 options at Model level - has root element and list of elements.  When X collection gets serialized,  should element property
       * element never be there (never serialized)
       * element is required (always serialized)
       * element is optional.(Serialization of the list of elements is optional for the producer.)   Producer can put root element and list of elements. 
* Jeff: Are we making this over complicated?   Would a count just work?   Gary: not sure really needed. 
* Two decisions needed:  do we list elements;   also have issue of root element vs. document describes. 
* Want to make sure we can have multiple SBOMs in same serializations...   multiple possibible starting points. 
   * XCollection helps you when parsing when SBOMs including others (David K), only a short cut when know all the elements and know where they fit in the graph.   Known unknown should fit in element.   XCollection should fit in document describes. 
   * Sean - example SBOM and 2 person elements.   Would all be root elements. 
* Bob - Hardware BOM - say what it is saying you, but have an additional/missing piece.   Would communicating what you should get?   Gary:  Payload is like the packing list.   If deserialize, should be covered in either case. 
* Poll relative to issue number 505. 
 * Is the list of elements:
  * 1: required to be in the serialization. 
  * 2: excluded, required not to be in the serialization
  * 3: optional in the serialization.
 * Results: Excluded (optional received the second highest number of votes).
Gary: The decision is to exclude it for now, as it can be added back without causing issues in version 3.1. Most people prefer this simpler option.

## Issue 495: 
* Agree this is a problem we need to solve
* Current descriptions indicate a semantic difference between rootElement and describes
  * Sean and Gary's recollection is that rootElement was supposed to replace describes
Gary curious about Max's opinion on having both.
Value in having both?
Consider separating decisions.
Agreement that there is a problem with the existing spec.
First decision: Do we need two different ways of represemnting the roots? or i sthere only one way?
* Do we need two ways of representing the root? One technical and one intent. Value in that?
* Root element: https://github.com/spdx/spdx-3-model/blob/main/model/Core/Properties/rootElement.md
* Fix spec description of root element
* Strong consensus from the group-that we only want one way to do that. Should it be a property or a relationship?
* Property or relationship? Sean/Gary: It should be a property. No disagreement from the group.
* What is the name of the property-Stay with route collection and/or change it to describes? Gary: we keep the current naming so we don't have to discuss it. Sean concurs. 
* Description of describes: Every to Element is described by the from Element. This can be used to denote the root(s) of a tree of elements contained in an SBOM.
* Root collection or describes- keep current naming so it doesn't need to be discussed. Group agreement. Drop the "relationship describes".
* Create pull request to correct description- corrects the description and removes the describes property or relationship in one pull request just as a fix to issue number 495. Gary to do PR. This to be the basis for discussion during next week's meeting.
* Refer to PR500-defines what SPDX document should be.
* Name change? Xcollection to something else? Serializable collection? (Sean)
* What do we do with SPDX document? What should it be?
* (Gary) Need two elements, possibly three: a different name for what is in the payload, serializable collection for what is before the payload, and a serialized element to representwhat has previously been serialized.
* This discussion to be picked-up on Serialization call. Think about different proposals. David's proposal?  Gary had written something up. Sean, ideas?

## Decisions
* Exclude 'element' for now as the simpler choice
* Question: (1) Drop document describes, (2) keep both, (3) keep both but change document describes to a property. Determination: Drop relationship describes.

## Action Items
* Relationship:  Known/Unknowns to be added to agenda for 10/10 meeting
* Relationship: Document describes semantically similar to root element property;  may need to detangle
* General meeting this week: move Serialization one hour post-General. Noon to 1 (ET). This week’s serialization meeting on 5 October will be moved out 1 hour to not conflict with the general meeting (9AM Pacific time). Gary to send out email to group.
* Looking for examples of build profile in JSON-LD.   Nisha will work on PR for the playground.  Gary volunteering to review example when available.
* Gary to create pull request to correct description.Basis for discussion next week

## Next SPDX Tech Team Meeting 2023-10-10
* Kate- Relationship proposal to be reviewed
* William- documentation update
* Follow-up from Serialization meeting: 05 October
* Corrected root description discussion.
