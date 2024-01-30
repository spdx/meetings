## SPDX Tech Team Meeting 2023-11-14

## Attendees
* Kate Stewart
* Sean Barnum
* Matt Rutkowski
* Joshua Watt
* Bob Martin
* Jeff Licquia
* Marc-Etienne Vargenau
* Adolfo Garcia Veytia
* Arthit Suriyawongkul
* Max Huber
* Rose Judge
* Karsten Klein
* William Bartholomew
* Bennet Pursell

## Agenda
* Sorting through Relationship PRs (security: https://github.com/spdx/spdx-3-model/pull/550;  general: https://github.com/spdx/spdx-3-model/pull/548)
* ElementCollections have 0:   https://github.com/spdx/spdx-3-model/pull/552;  with constraint?
* Additional SoftwarePurpose types:  https://github.com/spdx/spdx-3-model/pull/554
* More encoding notes from Yocto encoding
* Documentation Generation (William last 30 minutes) - Alexios & William to deconflict scripts

## Notes
## 548 - clarify relationshipTypes
  * Joshua has pushed a bunch of fixes -- applying so we can do more work on top of it.
  * Rose will rebase security PR on top of the merge

## 550 - Clarify security relationshipTypes
  * Try to organize definitions with from first - reads more logically
  * Rose will go through and rearrange - add examples "from coordinatedBy to" at the end of the line if you cannot make the sentence make sense in English
  * Rose will incorporate comments after the call - Kate will look for changes and merge
  
## 552 - Allow ElementCollection to have 0 elements
  * Are contraints to be written out in plain text? For now, yes, but long term goal is to write out ecoded as SHAQL
  * Do we need `minCount:0`? or is this implied?
    * Consensus is that it doesn't hurt for clarity.
    * If we do delete it then we need to take a pass at other files which does have the minCount:0 contstraints.

## 554  - Add diskImage and filesystemImage SoftwarePurpose
  * There would be some overlap with firmware exisiting type
    * The firmware purpose was to interoperate with CycloneDX
  * diskImage may not be software - digital artifacts
  * firmware clearly has a different lifecycle than other things
  * So we can't have a software package that's a disk image? What to use instead?
  * CDX is trying to move away from enumerated types like this completely
  * If the person looking from a domain perspective is strongly in favor or something, we usually add it
    * Therefore, OK to approve and add diskImage and filesystemImage.
    * Should still probably clarify that firmware is meant to be the small parts as opposed to the aggregation
    * We can merge this and add the clarification of firmware later
* Missing two from CDX 1.5: `deviceDriver` and `platform`
  * @puerco will compare and open a PR: https://github.com/spdx/spdx-3-model/pull/555

## Encoding Notes from Yocto
  * Currently elementCollection (base collection object) has an imports field but feels like it's only intended to be used by SPDX document?
  * Yes, import, which is the externalMap and namespaceMap, is moving to SPDX document and away from Element so you don't have nesting of those things which causes complexity
  * If I have an SBOM does it need to be inside an SPDXDocument when I serialize it? yes
    * If you are passing the SBOM element then only the SBOM element in the lement list? no the SPDXDocument must  have all Elements that are being serialized, regardless of if they contained in a (sub) ElementCollection
    * "element" list of the SPDX document has to be all the elements in the SBOM

## Document Generation - William
  * Walkthrough of exisiting docs
  * Some of the stuff William is working on conflicts with Alexios' work - William will followup with Alexios
  * Can we produce PDF or printable page type version of the spec from this? Yes, mkdocs is still doing all the driving and still has multiple output formats 
  * Can we have class diagrams included in the rendered docs?  Yes, on the plans to have ancestors & descendant classes.
  
## Diagram update
  * work in progress,  requesting that the changes be logged.

## Decisions

## Action Items

## Next SPDX Tech Team Meeting 2023-11-21
