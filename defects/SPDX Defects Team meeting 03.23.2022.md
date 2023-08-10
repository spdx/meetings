## SPDX Defects Team meeting 03.23.2022

## Attendees
* Dick Brooks
* Thomas Steenbergen
* Rose Judge
* William Cox
* Anthony Harrison
* Christian Long
* Karsten Klein

##Regrets 
* Jeff Schutt; conflict with NIST/OMB workshop on US EO 14028

## Agenda
* General
* Approval of minutes of last week's meeting
* Other topics / news
* Adding linking to security vulnerability information in SPDX 2.3

## Notes
### General
*  Any objections to approving https://github.com/spdx/meetings/pull/139? No objections, Thomas merged
 * Other
 
### Adding linking to security vulnerability information in SPDX 2.3
* Recap of all the proposals: https://docs.google.com/document/d/1A9lOwYrpVlmxBl_cEahZTMeo0gU6yDxkgSbx4I5K5v4/edit
  * 4a - adds 'type' options to option 2
  * 4b - different variation to 4a - instead of using SECURITY category, introduces new categories for particular information (VEX and vulnerability_identifier)
  * 5 - adds two new types (VEX and vulnerability_identifier) as well as a "comment" field with preset tagging options
* Opinions?
  * Rose and Dick - option 5 is too complex.
  * Thomas: [in regard to option 5] comment should be free form text, not pre-decided "tags" or input
  * Anthony: [regarding option 4a] agrees with Dick - want to avoid adding status information to SBOM given that vulnerability status can change over time and we don't have to re-issue the SBOM. Christian agrees.
  * Thomas: don't want to include status, want to give folks options to link to vulnerability information.
  * Rose: keep in mind this is a short term fix; we can elaborate these categories in 3.0
  * Option 3 is essential option 3+2. Option 3 is recommend use of at least one package identifier (CPE/PURL) using External Reference
  * Christian: choice between option 1, 2, 4a, 4b, or 5 to go along with 3. 
  * Anthony: option 2 but still need to decide on referenceTypes that we want
* Dick: let's keep in mind that we are needing to address NTIA minimum requirements.
* Thomas: we are also trying to address current issues that open source communities are facing. Let's go beyond the minimum.
* Christian: Option 4a motivation was interoperability with other standards (like VEX)
* Rose: I wonder if we can keep it to types that don't imply status while expanding interoperability. i.e. maybe "fixed" can correspond to "fix"
* Review of referenceTypes:
  * "Advisory"
     * Definition: A published security advisory for the vulnerability
     * No objections for this as a referenceType but Anthony wants to remove "informational_advisory" and "security_advisory" from the types and keep a more generic option
     * Dick: does advisory point to a single CVE? Thomas: yes
     * Dick: if a new advisory becomes available, do I need to re-issue an SBOM?
     * Karsten: two different usecases being described: 1) having a complete SBOM with product information 2) vulnerability status report based on this SBOM that adds all the status, advisory, etc and this depends on the SLA with your customer; Option 3 means that the static SBOM has all the information required to do the querying and convey vulnerability exposures.
     * Dick: I agree, but there's information that may not be received through that route (i.e. vendor fix status)
     * Anthony: the VEX document would give you the dynamic statement - like a triage document
     * Thomas: advisory is more static; but you could have the static vs dynamic discussion with link (i.e. fix is more dynamic vs advisory more static)
     * Thomas: We should separate types based on dynamic vs static referenceTypes
* Anthony/Thomas: advisory, disclosure, fix and web seem like bare minimum referenceTypes that we want to have. We can describe a lot of cases with this.
* Rose: prefer 'url' to 'web'
* Christian: even the most static SBOM could have to be re-issued if a new advisory comes out tomorrow (general "yes" consensus from the group)
* Dick: can we get rid of the types that are just noise? Does anyone need swid?
* Christian: It's fairly easy to extend these types after 2.3, right? (yes)
  * "Disclosure:
      * Definition: A link to a vulnerability response
      * Thomas: Do we call it disclosure or do we call it something else? i.e. descroption, others?
      * Dick: This word answers the question "what is the current vulnerability status". Perhaps "vulnerability_disclosure"
      * Dick: implicit approach is cyclonedx vex, explicity approach: sbom vdr - list each and every component along with their vulnerability status
      * Dick will work on wording for the "disclosure" definition to try to describe a "carfax" comparison.
* Next week we will nail down definitions for option 2 and have a proposal for general SPDX tech call. Consensus for 2.3 is Option 3 + 2 minimum
* Karsten: There are different types of advisories/notices/updates/news so we need to consider the different sources to make the best definition
