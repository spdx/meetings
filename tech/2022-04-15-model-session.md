# SPDX 3.0 Model Session - April 15, 2022

## Attendees

* Alexios Zavras
* Bob Martin
* David Kemp
* Gary O'Neall
* Henk Birkholz
* Jeff Schutt
* Kate Stewart
* Nisha Kumar
* Sebastian Crane
* William Bartholomew

### Regrets
* Sean

## Agenda
* Open Questions

* 3.0 Model

## Notes

* Henk:   How handle Snippet & File relationships?
   * Kate:  Use "Contains" relationship.    William agrees keep Contains for physical
### 3.0 Identity discussion
* Regrets Sean isn't here
* William - continue discussion from tuesday
  * We break out the things that represent a person as individual entities
  * We then add the concept of "subject" as someone who took action
  * Thought?
  * Bob - what does core need to do its job vs what should go into a profile (pedigree and provenance) needs to be teased appart.
  * Consensus - agree that details can go into a profile

* David - Actions will have identifiers associate with it.
   * Splitting out the identifiers from actor, and separated from action.
* Sebastian - please describe the semantic description of actors.
   * It represents who took the action.   Capturing the physical of what happened.
* Gary - looking at required fields, are there cycles introduced into graphs.   Should we consider it doesn't subclass from element?    Concern want to see github and email being separate identifiers.   (+1 from David)
* William - what is in core, and there may be a simplification.
* Addressing subject from outside current document - how much of this is desireable,  how much in core vs. something else.
* To what extent is a collection created by an actor (ie. document scope in 2.2).
* With these being properties, hard to build up later.

* David - CreatedBy is an Action performed by (on-behalf-of) an Actor as evidenced by a Credential.  A credential could be long-term (cert) or short-term (session ticket) I'm not sure there is a difference between Actor and Credential; maybe we should describe Actor as "authenticated user", where the authentication strength could be low (self-asserted) or higher (attested by something trusted).
* Gary O'Neall says:There may be something there on separating out the subject used for creating an element vs. other use cases.  This may solve the recursion issue

* William:  Separate what is known at the time an event occurs.
* Open Question:  Does it matter if known if an Actor is person or an organization
* William:  Which subject relates to which actor, may change over time.    Trying to follow the NIST digital identity definition
* X 509 - more than one identifier on same actor.
* Kate:   How represent tool?
  * NIST has different subject type to represent tool
  * Tool is this package.
  * What software was running as a process that created/combined these files.
* Gary: concern about complexity on created by - may need to treat different than entity relationships.
* Alexios:  have an element creator?  which is very specific.
* William would be just a name and one or more identifiers.
* Gary:  Recognize, don't need subject capability.
* William:  Actors are local to documents.    Identifiers and subjects that link things together solve problems.
* Henk:  trying to understand
* William:  Subject are like integrity methods, could be part of element or document.    Diff between a struct and class.   Subject that inherit from element, has class semantics and access by reference.
* Henk:  Actor at document level, speaks for all the element.
* Gary: I'm really starting to like this.  Having Actors be local to the document solves almost all my complexity concerns.
* William:  Originator is a subject, and subject could be a tool.    We allow multiple.

* Gary: If want to preserve the person/organization/tool we can add a "type" property to Actor of type enumeration Person, Organization, Tool.  Subject identifier binding - annotations and other information, it's not about hte identifier itself, its about the binding betwen the subject identifiers.   Property between identfier, group 1:many.

* William - agree having type to this will be better than we have today.
* Gary - know on common use case,  created by - know the info.   Suggest SubjetIdentifierBinding relationship to Identifier bet 1..*
* David - Analogy to time (which is a complex type)  Identifer would be acting in a similar way.

* How do you bundle actors and artifacts?    We can't make an actor an element.   Actors need to be immuatable and represent a point in time.

* Subjects let you modell in more depth, but typical scenarios would not need.
* Identifier bundles can be created in points in time.   So have timestamp.
* Elements have a created date.   Releationships are elements, so have created date when it was set up.
* We've talked about a subclass relationship (from and to, over date range)

* AI:  Kate to work through ISO example with Henk.   He has some producer context he wants to understand the flow.

* William: There is not just one way to express when to generate an element, we need to keep flexibility.    Kate & Bob agreeing.

* Nisha would like to see some examples - to make it more concrete.

---
break
---

Review of punch lists
- element - need
- renaming of abstract vs. concrete classes.    AI:  Gary to create a list of where he sees explicit differences.
- we still have document, to refer to a collection.

- Package
  - CycloneDX just has distributable units,  interoperate with CycloneDX.   They think more of subclasses of packages - is there value in doing this?   ie. source packages,  single file binary packages,  service package over the wire, ...  unique property in sub classes.
  - What unique property on a source package?   simplicity of serializations?  different mental model.
  - We need better example.   see:  patterns & use cases.   Scenario to fill gap.
  - Example web site,  classes and data types in explorable manner is really missing in other places.   Curation system of how to add things, would be useful.   Prov-O specification is well organized.
  - Do we want to separate out the "types" of distributions.

  - Gary:   add things that are deployment mechanisms.
  - operating system information - what is running, is seaparate from what is delivered.
  - distributed blob vs.  configured & running.
  - Package file name today - only applicable if delivering as a file.
  - Nisha:  package purpose for 2.3 - container language example.    Differentiation between concepts.   What you are giving to someone else,   vs. supplier of,  vs. environment running in.     Person is supposed to understand using it.    Container "refers to",  rather than "consists of" due to reference by digest (manifest) receivers using pointer.   It's not a collection of files, its a structure, with limited set of tools that understand the structure.
  - William - its a logical collection of files, not a physical collection, so package is a logical set of files.   If one of the files change, the identity is forced to change.    From SPDX prespective its still a collection of files.
  - Nisha - how the collection of files is constructured is not known, but how it is constructed is not known.   When distributing and sharing containers,  how manifested on your file system, vs. on a server side.  Changes from registry to registry.   Consumer/generator don't know.
  - William - this gets into the art part of SPDX - it's a language.   SPDX doesn't tell you what you're trying to communicate to consumer of document.   How's its layed out registry so can do integrity,  vs how it's layed out on a client disk, so can do integrity check.  Can reuse underlying pieces.
  - Discussion with Nisha on container and container images.
    - Container:  runtime on file system.
    - Container Image is a collection on a registry.

    Both contain same files, but they way they manifest is different.
    Don't need to include it all.   Need to look at what is useful to the consumer.
    Example of Windows - millions of binaries into flat, and then variants of distribution artifacts are assembled.

William BartholomewWilliam Bartholomew says:I think it is "distributable" not "distributed", does it make sense to identify this set of things as something that has its own life cycle

Gary:  we may be missing some necessary "vocabulary",  do we have enough to describe for container and service?    Let's do some thought experiments.   subclass vs. peer of package.

We need a strong story about package --> file realtionship;   depricate  PackageFileName and replace with relationship and File Element (that would have filename for instance).

Distributed vs Deployed is a dimenstion that isn't really modeled effectively.  What distributed is different location, than how its deployed on a system.  This is somthing to be added to 3.0.

AI: Gary to comment in issue on Package/Filename about subtlety.   Here's what we should do to package to satisfy use cases.    Will describe solution for deployement and distribution.
