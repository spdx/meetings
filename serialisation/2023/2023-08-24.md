# SPDX Serialization Focus Group Meeting 2023-08-24

## Attendees
* Armin Tänzer
* Sean Barnum
* Brandon Lum
* David Kemp
* Maximilian Huber

## Agenda
* Brandon: Concern, that parsing gets complex

## Minutes
* Concern, that parsing gets complex
  * Sean: it depends on what you mean to be "hard"
  * Sean: what is the goal, parsing or generating a tree
    * Max: maybe the effort to parse it into a dependency tree
  * Brandon: parsing sometimes needs multiple passes, e.g. if the SPDXDocument comes at the end
  * Sean: it depends on the usecase
  * Brandon: some are usecase specific, yes
  * David: I am curious about the not-fitting in memory parsing
    * just assume to collect a map of IDs to elements
  * Sean: we could canonicalize the order of elements in a serializaiton
  * Max: Amends might break that concept
  * David: there might be cycles between collections
  * Sean: there are different approaches to streaming, open graph and closed graph
  * Brandon: yes, that makes sense
  * Sean: every collection can be interpreted as a closed graph
  * David: distinction in Collections vs. Documents
    * the graph is always open
    * every collection is closed
      * a payload could halve of a closed collection
  * David: having two root elements?
    * does not make sense for roots?
    * Sean: I can give context
      * `elemnt`s are all the elements
      * `rootElement`s are all in elements. it points to some which are the root. 
        reason was: one could have three roots if a collection contains three SBOMs and all are pointed out as roots
    * rootElement is also just a hint
  * Brandon: can we provide examples
  * Sean: a SBOM typically has one rootElement.
* Examples
  * Questions by Brandon:
     * completeness in open and closed graph thoughts
* David: there are two model element types that express cosedness. to-side of relationships and collections which imply completeness.  If you want to assert a "Package" is complete, the assertion can be made over a 1:n relationship, or by including all elements related to the package in a Collection (e.g., Sbom).
