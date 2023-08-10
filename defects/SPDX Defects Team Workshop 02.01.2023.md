## SPDX Defects Team Workshop 02.01.2023

## Attendees
* Dick Brooks
* Rose Judge
* Thomas Steenbergen
* Anthony Harrison
* Henk Birkolz
* Jeff Schutt

## Agenda
* Approve meeting minutes from last two meetings
* OpenVEX
* Continue to work on defects model

## Notes
### Approve meeting minutes from last two meetings
* https://github.com/spdx/meetings/pull/273

### OpenVEX
* OpenVEX was announced  https://www.chainguard.dev/unchained/accelerate-vex-adoption-through-openvex and https://github.com/openvex/spec
* CISA VEX, SPDX VEX, CycloneDX VEX and OpenVEX now exist
  * SPDX is it's own implementation? Easy translation between CISA VEX
* VEX roles seem to be standard strings for OpenVEX - should've been an enum - doesn't specify how, what and why
* Vulnerability and advisory would be a relationship in SPDX. OpenVEX sees it more as a data feed that is separate - completely loose from an SBOM, using purls.
* How do we link this to SPDX docs? Link as external refs - openvex doc would techincaly be an `advisory` (you could also use `url`)
* CSAF stuff is free format text which is really hard to parse. enums would be easier to parse and process
* Link to CVE or URL, but how will we find references to this? Assume that the consumer knows all the well known identifiers
* Timestamp is non standard format (https://www.ietf.org/archive/id/draft-ietf-sedate-datetime-extended-07.html)
* Has Linux Foundation gone on record endorsing OpenVEX? Yes
* To have a fourth VEX implementation is a litle concerning (with no defects group consultation)
* Concern about the messaging of this announcement and how it will affect SPDX adoption
* Rose and Jeff asked to maintainers for OpenVEX, can bring concerns to OpenVEX maintainers
* OpenVEX points to vulnerability - where can I find this? and product (purl) - how do I find the SBOM for this?
* What does the governments model look like? How do we support open source/startup as well as larger commercial vendors - this is not just a vulnerability problem; this is a balancing act in all aspects of software development.
* In order to understand the inventory of software, we need some standards and this is the same thing happening in vulnerability space right now. 
* Need mapping table from CSAF to CycloneDX and add OpenVEX
* NIST VDR links:
  * NIST SP 800-161 RA-5; https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-161r1.pdf 
* CycloneDX VDR Support: https://cyclonedx.org/capabilities/vdr/
* What is a NIST VDR: (has link to open source VDR examples):
    * https://energycentral.com/c/pip/what-nist-sbom-vulnerability-disclosure-report-vdr
* JSON version Example: https://raw.githubusercontent.com/rjb4standards/REA-Products/master/SBOMVDR_JSON/VDR_118.json
     
     "In summary, a NIST Vulnerability Disclosure Report (VDR) is an attestation by a software vendor showing that the vendor has checked each component of a software product SBOM for vulnerabilities and reports on the details of any vulnerabilities reported by a NIST NVD search. The VDR is a living document which the software vendor updates as needed when new vulnerabilities have been discovered and reported. A VDR is published whenever a software vendor issues a new or updated SBOM, including initial product release, making it available online, all the time, to all customers of the product described in the VDR. This gives software consumers that ability to answer the question “What is the vulnerability status of my software product from Vendor V, as of NOW?”.

### Continue to work on defects model
