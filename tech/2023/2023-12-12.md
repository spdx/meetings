# SPDX Tech Team Meeting 2023-12-12

## Attendees
- Sean Barnum
- Rose Judge
- Nisha Kumar
- Jeff Licquia
- Bob Martin
- Gary ONeall
- William Bartholomew
- Arthit Suriyawongkul
- Peter Monks
- Takashi Ninjouji
- Jeff Schutt
- Alexios Zavras
- Karsten Klien
- Rob Craig
- Yoshiyuki Ito
- Joshua Watt
- Tim Miller
- Victor Lu
- Adolfo Garcia Veytia

## Agenda
* Lite profile pull request #563
* ExternalId - pull requests #492 and #519
* Package integrity methods - issue #345, pull request #498
* Extension namespace - issue #433 and pull request #503
* Review of pull requests opened since last week #564, 575, 576, 577, 578, 579
* Conversion of packageFileName when it refers to a folder - issue #83
* LicenseList version SemVer format issue #429
* Annotation content type cardinality issue #565
* Expanded license overlapping terms - issue #573
* Review issues added in last tech call - make sure we have them covered.

## Notes

## Lite Profile
Yoshito and team created a documentation MMD file for the lite profile. They listed up some elements of the co-profile or software profile in the FMD file, but it had duplicated definitions. They discussed how to eliminate those duplications from official specifications.
  * https://github.com/spdx/spdx-3-model/pull/563
  * Decision: Eliminate duplicated info
    * No need to re-state description that is already in Core profile
    * Look forward to remove duplications in RC2 release
  * Mapping info
    * SPDX 3.0-SPDX 2.3-SPDX Lite mapping information will be provided (in an Annex)
    * Mapping information can be kept in a separate file

## Spec repo structure (SPDX 2 and SPDX 3) 
The group discussed adding annexes to the SPDX 3 spec repository beyond just the model represented by markdown files. There are other annexes that need to be added, which will be done after RC2 release. A separate chapter about using PDX slide was proposed, which can describe all constraints like having an SPDX id and license for core and light profiles respectively.
## Structure of SPDX Spec Repository
The group debated whether they should use a new repository or rename existing one from SPDX 3 model to SPDX 3 spec but not have two repositories as there is no overlap between them. Some members suggested having two repositories would make it easier to manage issues separately while others preferred one repo for ease of access by newcomers. However, everyone agreed that they want history preserved when creating new releases so people can see what led up to current version with known issues included in it. 
## Integration of website and spec creation components 
Question asked regarding if there would be any issues with integration if each component was in a separate repository. Group responded that it was perfectly fine for generation across repositories, but combining them into one specification could not be easily merged and integrated. Suggestion: dynamically switching between websites to provide the same experience for users. 
## Repository for SPD 3 spec 
Should the SPD spec repo be maintained or Should a new one be created or combine the model in that. Gary preferred to have a single repo, while Sean proposed starting with a new one to see what's happening there and then transferring the spec later. 
## Clean up of issues in SPDx Spec Repo
It was suggested that the group go through all of the issues and clean them up no matter what. They need to verify all these issues are taken care of before deciding on anything else. 
* Discuss on repo structure, should be in one or two repos?
* Concerns on automatic document generation
* If two separated repos it means issues will be reported in two different places
* Second repo is opportunity to start fresh, but there are legacies to be clean up in anycase
* Importance of keeping history in a place that people can see it
* Also depends on whether we like to keep the development of SPDX 2 and 3 in parallel for long time or not
* If SPDX 2 will be kept updated only for short period, for transition purpose, it may make sense to have one repo
* If SPDX 2 will be kept update for a longer term, in parallel with SPDX 3, it make sense to have 2 repos
* **TODO: Need more time, push it to next week. A small group can be organized to discuss.**

## Memory Safe Language
### Capturing language information in Sbomb 
Concerns raised about moving towards memory safe languages, which led to the question of how they can capture language information in an Sbomb? It was noted that it is not captured anywhere right now but could be added as an issue under safety profile team.  It was further suggested that the discussion deserves more time and should be tabled for next week's agenda. A small group could also have a separate meeting to discuss the topic and propose a branching strategy for the spec. It was emphasized that there are other issues to address, which are beyond RC2 issue.
  * Information about language that use to build the software (which may useful to tell about safety of the software components)
  * Target the Safety Profile first, and if no response we can take it back
## External ID (https://github.com/spdx/spdx-3-model/pull/492)
  * Jeff S. raised a concern; was not on the call, so may need clarification (comment on PR from Oct 18)
  * ExternalIdentifier as specifically a non-SPDX ID, vs. ExternalIdentifier possibly being a SPDX ID identified with that type
  * spdxId == ExternalIdentifier ID for SPDX external identifier type?
  * Copying use case is a potential problem; references to internal copies may be difficult, as opposed to external references (ExternalMap)
  * Possibly post-rc2 issue; open a separate ticket
  * Will close this PR and Jeff will open the new ticket
## Package Integrity (https://github.com/spdx/spdx-3-model/issues/345)
  * Gary filed and made a proposal; Jeff S. made an alternate proposal
  * PR #498 by Gary; lots of comments, possibly not as clear as it needs to be
  * Queue up for week after next or later
## License Related Issues
There are several license-related issues that need attention, including listed licenses with centralized repositories, network isolated air-gapped devices needing access to information, copying scenarios, and defining SP external SPDX ID in the external map. These issues will be addressed during future meetings. 
## AIs
- [ ] Add annexes to the SPDX 3 spec repository after RC2 release 
- [ ] Decide on structure of SPDx Spec Repository (new or rename existing one) 
- [ ] Clean up issues in SPDx Spec Repo before deciding on anything else 
- [ ] Capture language information in an Sbomb as an issue under safety profile team 
- [ ] Update poll request related to light profile documentation and get it approved by Alexios for merging
- [ ] Describe details about MACDFIRE in annexed documentation regarding package L or LI being optional or mandatory for light profiles
- [ ] Provide input on issue 345 regarding integrity method for packages during next week's call
- [ ] Pick up discussion from where left off previously about Extension Name Spaces
- [ ] Address several license-related issues including listed licenses with centralized repositories, network isolated air-gapped devices needing access to information, copying scenarios, and defining SP external SBDX ID in the external map

=====================================================================
