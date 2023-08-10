## SPDX Defects Team meeting 04.06.2022

## Attendees
* Thomas Steenbergen
* VM Brasseur
* Karsten Klein
* Jeff Schutt
* Bob Martin
* Henk Birkholz
* Matt Weber (Collins Aerospace)

## Agenda

* General
* Approval of minutes of last week's meeting -> Thomas / Rose to merge in the suggestions from Dick & Jeff and then merge
* Agenda for the tomorrow's agenda

## Notes
* 
* Align on the wording for "Recommend use of at least one package identifier (CPE/PURL) using External Reference" to include in the SPDX 2.3 specification
      Stretch (if time permits)
* Discuss a new Security Type type for GitBOM / SWID - enable more format to be listed

Henk: Is adding identifier types helping 
Jeff: How do we tie the SBOM to external references
Jeff: Seperate location / identifier 

Workshop Agenda
* Principles / framing the discussion

The below principles guide the decisions our decision making. Note they are not rules, but when they are violated it should be done intentionally.

 It's patch/bandaid - will not solve everything
Optimize for adoption
Easy understand for community members how to create a SBOM
Minimize changes to existing software development practices and tools
Leverage existing public specifications that are already adopted in the community
Define how to translate between current SBOM formats
Optimize for automation
Leverage existing public specifications (but not to the detriment of internal consistency)
Platform and format independent
Supports machine translation between formats
Extensible where needed

* what do we want to include? (e.g. advisory, gitbom-id, (co)swid tag-id) nail down scope: e.g. include fix info?
* agree upon definitions, rely on existing definitions in other standards (e.g., advisory)
* how to include in the spec?- identify the "socket" in the spec:   Category, ReferenceType, Comment
* Draft into SPDX 2.3 spec - actual text in the specification - Annex F External Reference
