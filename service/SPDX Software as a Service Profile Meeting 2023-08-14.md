# SPDX Software as a Service Profile Meeting 2023-08-14
## Agenda
* CISA Update - Nisha
* Continue discussion on use cases:
     * See https://docs.google.com/document/d/149PcR_KjyWKLk0fMgujoWRtVkEikcohD2u3BBmY4pS8
  * New use case proposal - access to security related logs (e.g. audit logs)

## Attendees
* Gary O'Neall
* Nisha Kumar
* Jeff Schutt
* Ivana Atanasova

## Minutes

### CISA Update
* Community that is currently discussing SBOMs for SAAS - still working on "how is SaaS different?"
* Still in discovery phase - more of a product mindset
* Focused on satisfying the EO edict for SBOM - 
* Service transparency currently on hold while working
* Perhaps we can present our work back?
* OpenSSF is interested
* Suggestion: present to OpenSSF first
* Target European summit - could meet with OpenSSF then
* Could get feedback on this call and other mechanisms - 
* Once we finish the use case documents, post to SBOM Everywhere slack channel - link to doc for review, open it up for comments - 

### Use case updates
* See https://docs.google.com/document/d/149PcR_KjyWKLk0fMgujoWRtVkEikcohD2u3BBmY4pS8/edit
* Discussed if we should provide some examples in JSON before sharing with OpenSSF
* Discussed what information would be shared internal to the service provider and what would be shared externally
  * Related to licensing
    * May mandate publishing information
    * Reference https://opensource.org/licenses/ - This lists all the approved licenses by OSI
    * Specific example: Affero GPL requires information to be available on software used under that license
    * Suggestion: Add a use case for license compliance where information must be made available
  * Related to policies
  * The standard needs to take these into account
  * Could take into account the role of the requestor
  * Proposal - add information to the use cases if it is internal to the organization or external - propose we prioritize information shared across the organizations
  * Related work being done https://cloudsecurityalliance.org/artifacts/the-continuous-audit-metrics-catalog/ - should include
  * CISA sharing workgroup - more on the mechanisms to support sharing
* DECISION: Agree we should focus on information that should be shared across organizational boundaries - should leverage other standards / forums already discussing important metadata for a cloud service that should be shared
  * Make a pass at use cases and denote which use cases:
      * clearly involved sharing data across organizational boundaries (External)
      * clearly does not does not involve sharing data across organizational boundaries (Internal)
      * not clear or mixed (Unknown)
  * Jeff will make a pass at the use case document
* Reviewed use case document up to "Verify if user data is encrypted"
