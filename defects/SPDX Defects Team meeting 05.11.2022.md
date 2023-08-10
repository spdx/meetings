## SPDX Defects Team meeting 05.11.2022

## Attendees
* Thomas Steenbergen
* Rose Judge
* William Cox
* Henk Birkholz
* Jeff Schutt

## Agenda
* Approval of [meeting minutes from last week](https://github.com/spdx/meetings/pull/150)
* Update on Defects contributions to 2.3 Spec
* Continue work on Defects Profile in 3.0 Spec

## Notes

### Approval of meeting minutes from last week
* https://github.com/spdx/meetings/pull/154 - Approved by VM and TS; merged

### Update on Defects contributions to 2.3 Spec
* https://github.com/spdx/spdx-spec/pull/658 External References change to add security related types was merged on May 11 into 2.3 branch
* https://github.com/spdx/spdx-spec/pull/670 Annex G with security scenarios was discussed in SPDX tech meeting from May 11, recommendation was not to wait for other noon-Defects contributors to Annex G.

### Continue work on Defects Profile in 3.0 Spec
- Rose: will 3.0 be backwards compatible with 2.3? (i.e. the same information collected?)
- Jeff: natural that it won't be compatible 
- Thomas: you will be able to translate between 2.3 and 3.0 but might lose some information from 3.0 to 2.3
- Henk: 2.3 to 3.0 should be loss-less (group agreement)
- 3.0 charter work: https://docs.google.com/document/d/189VtcPVCVZGl5j1NZL4HTO54iQAWtVwn6wcDHkDiHFQ/edit 
- Scope: This team recommends enabling custom attributes using a registry, e.g., on the SPDX GitHub project site or the ICANN IANA registry.
- Rose: Will we be able to use the same exisitng IANA types for SPDX 3.0 profiles or will SPDX profiles have different document extensions? (We currently have tag value and json IANA types)
- Thomas: let's pose this question to the core team about what to do
- Should we cover all information available in a CVE database in the 3.0 spec?

Punch List
* Define Usage Scenarios the team cares about
* Create a survey to crowd source usage scenarios
* Identify the minimum data fields required in SPDX 3.0 that we must include in the Defects Profile to understand what type of SBOM data would have to be rewritten when a new vulnerability is discovered.
  * Can we create a defects SBOM that is lightweight data container which only contains the pertinent information and doesn't duplicate other component data?
  * Do defects SBOMs have to link back to product SBOMs?
