## SPDX Defects Team meeting Workshop 04.07.2022

## Workshop Agenda
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

consensus: type to describe security vulnerability information using a URL
consensus: to strongly recommend package identifier, e.g. CPE or PURL

Proposal 

 - Update set of identifiers with GitBOM, SWID
 - Vulnerability info:
      Advisory: new vulnerability is discovered and it is included in these package [representing product(s), FOSS, etc.]
Disclosure: here is my package [e.g. product] and reported vulnerabilities for include SW and my statement if they are applicable 


affected_info:

disclosure: revealing the 

security_incident_response: to provide a response to a security breach or incident
informational_advisory: to provide information which are not related to a vulnerability but e.g. a misconfiguration
security_advisory: to provide information which is related to vulnerabilities and corresponding remediations

* agree upon definitions, rely on existing definitions in other standards (e.g., advisory)
https://www.iso.org/obp/ui/#iso:std:iso-iec:29147:ed-1:v1:en
https://docs.oasis-open.org/csaf/csaf/v2.0/csd01/csaf-v2.0-csd01.html#12-terminology
-> advisory: reporting item that describes a condition present in an artifact and that requires action by the consumers
-> VEX: Vulnerability Exploitability eXchange - enables a supplier or other party to assert whether or not a particular product is affected by a specific vulnerability, especially helpful in efficiently consuming SBOM data.

Fix definition: 

A reference to the source code with a fix for the vulnerability (e.g., a GitHub commit). 

* how to include in the spec?- identify the "socket" in the spec:   Category, ReferenceType, Comment
* Draft into SPDX 2.3 spec - actual text in the specification - Annex F External Reference

GitBOM / SWID type addition:

SWID under category Security F2.3 SWID type (Concise SWID https://www.ietf.org/archive/id/draft-ietf-sacm-coswid-21.html)  -> Action item for Henk propose the paragraph for SWID
GitBOM under F4.2 GitBOM -> Action item for Jeff, propose the paragraph for GitBOM

Ideas:
- Recommended practices for which information to include in which fields
- Guidance on limitations to the current approach (a patch) and hints of what's to come in 3.0

For next call:
    * Will v2.3 be pushed to ISO? Who will drive that?
