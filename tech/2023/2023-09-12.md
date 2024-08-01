# SPDX TECH TEAM Meeting 2023-09-12

## Attendees
* Andrew Reiter
* David Edelsohn
* David Kemp
* Dick Brooks
* Gary O'Neall
* Jeff Schutt
* Jennie Kauffmann
* Karsten Klein
* Kate Stewart
* Marc-Etienne Vargeneau
* Matt Rutkowski
* Nisha Kumar
* Norio Kobota
* Peter Monks
* Rob Craig
* Rose Judge

## Agenda
* Namespace discussion update
* Update on the doc generation – William 
* Review proposal for definition restrictions at the profile level (including relationships): https://github.com/spdx/spdx-3-model/issues/462#issuecomment-1714744171 
* Try to close on the     profile PR – https://github.com/spdx/spdx-3-model/pull/447 
* SPDX ID Type for SPDX Property – needs David and Alexios: https://github.com/spdx/spdx-3-model/pull/407 
* General review of the 31 open issues targeted for RC2

## Notes
* Update on namespaces—2 meetings last week
* First meeting—2 different proposals. Both proposals are changes to the model. The most significant difference between the two proposals is that there exists a class in the model which is structurally identical in both proposals. However, in one of the proposals, the definition of this class essentially prohibits its inclusion as an element. This definition can be regarded as a structural one. 
* Second proposal—the semantics of this class pertain to the serialization of SPD X data. There exist diffrenet views on the optimal approach, with some advocating for simplicity and others advocating for a more rigorous approach. This topic will be revisited during a meeting on Friday. Let Gary know if you want to join the call. Call is 9:00 (PST).

*  Reviewed proposal on how to code up profile restrictions for properties and relationships
  * Discussed this with Japanese team last night,  they discussed further,  and Kobota-san confirmed that they can work with this approach
* Discussed the relationship restrictions 
  * Min & Max - number of relationships of this type.    Count seems to be ambiguous.
  * Why restrict min count - example is must have 1 and only 1 concluded license in licensing profile.  DIscussion on count is ambiguous term.   Discussed mininstance vs minrelationship - ended up going with minrelationship as term.  Ditto for max. 

* For a specific relationship type - restricting the from/to classes?  
  * Looking at additional restrictions;  want to subclass relationship.  
  * See if relationship present, rather than understand a subclass.
  * Nisha: Build profile needs these restrictions on relationships. 
  * Jeff:  Challenge is how to go about implementing the solutions consistently.
  * Gary: Not sure there is a problem for two different ways to express same thing.   Problem is we can't express it without opening a new subclass.   Creates possible inconsistency.   
   * Nisha: Don't have explicit properties need to add for build,  just want to add relationship restrictions on "to".  Don't see a valid need to subclass. 
   * Jeff: because of differences between spec, can see the reason to have additional ways to express beyond subclasses.

* DIscussion on #447
   * Conformance vs Namespace at the Element level
   * Some concern about profile namespace - possible duplication of information, and lack of clarity.
   * Alexios proposal using URIs makes duplication obvious.   
   * Gary notes "intends" is verfied by parsing through the elements.
   * Conformance is an intention as well.
   * Some discussion on whether namespace is essential.   Some concensus on going with just conformance at this point.   We focus this PR on just the conformance.
* David - looking for an example with more fields beyond a conformance, to help folks understand. 
  

## Decisions
*  Tentative (until EOD friday) Decision: Add in capability to handle relationships as per https://github.com/spdx/spdx-3-model/issues/462#issuecomment-1714744171
* Decision:  Gary to adjust PR 477 to just be focused on conformance,  and have namespace handled later as a separate PR.   Gary will also make it clear in the definition of the profile conformance property that core is always assumed.

## Action Items
* Gary requests assistance in reviewing the document—PR number 447 and provide feedback by either approving it or offering specific suggestions.
* Let Gary know if you want to join the call on Fridat @ 9:00 (PST)—proposals on serialization of SPD X data

## Next SPDX [TEAM NAME] Meeting 2023-09-19
