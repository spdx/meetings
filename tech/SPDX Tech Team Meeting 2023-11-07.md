# SPDX Tech Team Meeting 2023-11-07

## Attendees
* Max Huber
* Rob Craig
* Peter Monks
* David Edelsohn
* Joshua Watt
* Jeff Licquia
* Gary O'Neall
* Rose Judge
* Dick Brooks
* Kate Stewart
* William Bartholomew
* Alexios Zavras

## Agenda
* Serialization - feedback on relationship name - https://github.com/spdx/spdx-3-model/pull/542#issuecomment-1796412335
* Serialization - feedback on external map size - https://github.com/spdx/spdx-3-model/issues/549
* Rename externalId to externalSpdxId  Issue 519
* Documentation and spec parser plans (Alexios, joining after 30 mins)

## Notes
* Discussed the serialization follow-up from the previous meeting and reviewed PRs.
* Clarification was made on current relationship definition in the PR for relating the serialized artifact to the logical form of the artifact.
* Discussed the change in terminology from logical in version 2.3 to physical artifact in version 3.0.
* Discussed RC2 and its compatibility with previous versions.
* Discussed issues with Python while trying to get the Jinja template to work.

## Issues and PRs - with assigned milestones
* #548 clarify relationships- Kate to take a pass and work with Joshua
  * Jeff to work with Rose on relationship types: Security related
* #547 postponed to 3.0
* #545 Change directionality of current output. Kate-RC2 milestone.
* #543 target for RC2
* #538 Postpone until Spec Parser is fixed. Max to do a manual fix. gary made note in PR.
* #536 AI target for RC2 Alexios and Jeff are needed for this PR
* #534 target for RC2
* #533 target for RC2
* #532 target for 3.0 GitHub action
* #530 can be closed
* #529 Licensing. Target for RC2
* #527 Documentation. Target for 3.0
* #525 Target for 3.0
* #524 Gary to merge licensing.md
* #523 target for RC2
* #521 Proposal for Lite Profile- Alexios neede to weigh in on this P. related to PR #523
* #519 Jeff is neeed for this one. Kate and William to decide.
* #517 Add Lifecycle relationship Constraints.
  * Nisha did not accept changes. Need to wait for her to resolve.
  * Gary tagged her in PR.
  * Will follow-up next week.
  * Should be target for RC2.
  * Kate reviewed.
  * Needs to be reviewed by Alexios.
* #509 Serialization Decisions reviewed and resolved. Merged. Gary made note in PR.
* #503 Requires Shawn/Alexios. Has outstanding comments. SpecParser related. Shawn and alexios need to sync up on this.  
* All issues now have milestones assigned.
    
## SpecParser Updates- Alexios Zavras 
* PRs need to be updated
* Gary to merge licensing.md PR #524
* Alexios rewrote Parser
* Current state processess correctly
* Generates files as per William's last commits
* replace existing Parser with this updated version. Simpler and generates good HTML.
* Alexios to push and merge so Jeff L can continue his work.
* Agreed to push and not wait for RDF- current RDF outputs not useable
* Alexios to do a PR to get a branch pushed out.
* William and Alexios to sync up regarding any merge conflicts.
* Jeff L will look at the two branches and provide feedback/coordinate changes.
* Problem- Jinja templates are not pulling down.
* Joshua made a website python module that has jinja templates: https://github.com/JoshuaWatt/bitbake-hashserver-web-ui. Joshua: if you use hatchling for the build and properly structure your repo, it will include all the files correctly.
* Jeff L offered to assist William with Python related issues.
* William to follow-up with Jeff L, Kate, Gary, Alexios

## Decisions
* Significant increase in number of fields in external map identified as potential issue.
* Gary proposed a solution compatible with current implementation.
* External map solution- not to fix in 3.0 and leave open
* 3.0 Serializing logical form and relationship, Gary to merge PR.
* Not to fix the external map solution in version 3.0 and leave it open.
* The name SPDXDocument should be kept.

## Action Items
* William asked about sponsoring https://squidfunk.github.io/mkdocs-material/insiders/ so we can use the "Insider" features in the generated docs. Rob to follow-up.
* Gary will not be available for the next two TECH meetings
* Rob will not be attending next week's meeting

## Next SPDX Tech Team Meeting 2023-11-14
