## SPDX Defects Team meeting 11.30.2022

## Attendees
* Thomas Steenbergen
* Rose Judge
* Jeff Schutt
* Bob Martin
* Henk Birkholz
* William Cox

## Agenda
- Approve past minutes
- Create slide for Open Compliance Summit for Kate
- Provide feedback for https://docs.google.com/document/d/1Yd7ZKAl1l67FAqGOjLcr6MTr2e2KyhIGsB1NZ6M24Ro/edit
- Continue on SPDX 3.0

## Approve past meeting minutes
Thomas was other occupied but was able to catch up
- https://github.com/spdx/meetings/pull/247, approved
- https://github.com/spdx/meetings/pull/249,  approved
- https://github.com/spdx/meetings/pull/248,  approved
- https://github.com/spdx/meetings/pull/250,  approved

## Provide feedback for SPDX Outreach doc on SPDX and Security
Thomas: After the meeting please provide feedback on https://docs.google.com/document/d/1Yd7ZKAl1l67FAqGOjLcr6MTr2e2KyhIGsB1NZ6M24Ro/edit

## Create slide for Open Compliance Summit for Kate
SPDX Defects WG that were presented in SPDX General
https://docs.google.com/presentation/d/1sKRHQV--tOo2mjBqHNdXy9YnSDlLOsaFgThtd5RjcIw/edit?usp=sharing
2.3 Highlights:
    * From [Differences from Previous Versions](https://spdx.github.io/spdx-spec/v2.3/diffs-from-previous-editions/)
* Added hash algorithms (SHA3-256, SHA3-384, SHA3-512, BLAKE2b-256, BLAKE2b-384, BLAKE2b-512, BLAKE3, ADLER32 ) to the set recognized by 7.10 (Package Checksum field) and 8.4 (File checksum field)
* Update Annex F ( External Repository Identifiers ) to expand security references to include advisory, fix,  URL, SWID. Expand persistent identifiers to include gitoid.
* Update Annex G ( SPDX Lite Profile ) to include NTIA SBOM mandatory minimum fields as required.
* Added Annex K ( How To Use SPDX in Different Scenarios ) to illustrate linking to external security information, and illustrate how the NTIA SBOM mandatory minimum elements map to SPDX fields.
3.0 Highlights:
 * Similar to 2.3, we plan to support in 3.0 linking to various security information including CSAF/CDX/VeX and VDR
 * In addition to linking, we are evaluating minimal elements to embed in SPDX to convey security info in a simplified manner
    * Security Profile will inherit from Core Profile
    * Plan to define Security Profile relationships to Software Profile, Build Profile, AI-ML Profile, Hardware Profile, etc.
    * Intent to separate security profile metadata from SBOM metadata (snippet, file, package) and use relationships between the two
    * Working to support minimal VEX data fields in SPDX 3.0

3.0 Security Profile Blockers: 
    1) Time of participant
    2) Items needed from SPDX Core not always clear, Defects WG is planning to schedule some 3 hour workshops to move the profile  forward
    3) Security profile needs the concept of a product (upcoming blocker)
    4) Need for the [W3C Prov-O](https://www.w3.org/TR/prov-o/) provenance ontology, e.g. to enable security agents to act on SBOMs

* Would be nice to have the concept of a product in SPDX 3.0; currently there is a top level package describing the software running on a product
  * could we have a bare minimal product profile that inherits from element and has optional relationships to software and hardware
 * SBOM must be associated with a product; product could contain hardware and software
 * Top level package is typically representitive of the product
 * Henk:  Henk argurmented that we need a product in SBOM as a concept see for details https://www.ntia.doc.gov/files/ntia/publications/henk_birkholz_et_al._-_2021.06.16.pdf
 
 ### Continue SPDX 3.0 Discussion
 Propose to do a series of 2-3 hour workshop to move SPDX Security Profile forward

Workshop dates
Thursday December 15 7-10pm CET / 1-4pm ET / 10am-1pm PT
* Yes: Jeff, Bob, William, Thomas, Henk, Rose
* Maybe: -

Wednesday December 21 7 - 10 PM CET /  1pm - 4pm ET / 10am - 1pm PT  
 * Yes: Henk, Thomas, Jeff, Bob for 2/3, William
 * Maybe: Rose
 
 Use Cases to Address:
* linking to external security info
* SPDX SBOM including NTIA Minimum Elements
* SPDX document containing VEX Elements, i.e. from [1](https://docs.google.com/document/d/1uZPzQUoeoaCTaEmd7nQDf4lCl5ctpsNANh0phNC7IL0/edit#heading=h.p17rp4dt3ywo) and [2](https://docs.oasis-open.org/csaf/csaf/v2.0/csd02/csaf-v2.0-csd02.html#45-profile-5-vex)
* relationships between the SPDX SBOM and SPDX VEX info
* product <->  security info
 
 Outcome of the meeting
 - Set up in Google doc the docs similar to spdx-3-build-profile/model at main · spdx/spdx-3-build-profile (github.com)
 - Use next meeting to create a punch list with reference material so that in the workhop we can focus on decisions (We are re-using SPDX 3.0 Defects Punch List - https://docs.google.com/document/d/1qUgIbQbR3veBzT48XzUVZDddBtvjj05ibNxI1dzdRKw/edit#heading=h.gzkf9en0y7tu)
 - In the workshop we will create model
