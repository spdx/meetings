## SPDX AI team minutes, July 27, 2022

## Attendees:
* Kate Stewart
* Karen Bennet
* Jim St. Clair
* Gopi Krishnan Rajbahadur 
* Chris Shenefiel
* Derek Kruszewski
* L Jean Camp

## Agenda
  * Profiles - combining AI Application, AI Model,  AI Dataset

### Notes
   * Continuing discussion where we left off.   
   * Side discussion - scraping public datasets is ok.  
   * Been refering to files ... possibly uplevel to package for fields.  AI:  Kate to do a pass at dataset profile and figure out better mappings with 2.3 package fields.
   * Checksum - nice to have, but stream of data wouldn't have it. 
   * Consent - Was consent obtained, permission to share data set - do we want to split it up.   "Public" and "Guarded"  - talks about access expectation of License agreement.
      * Jim: There really isn't a consent agreement model when it comes to AI training sets. Health data is supposed ot be "de-identified" and as such isn't required to obtain any consent.    Consent for sharing?
      * GDPR - regulatory compliance;  EU Guidelines;  Chinese;  NSA ... "Access Guidelines" vs. "Regulatory" - Data subject owner permission.  Data subject owner permission.
      * Consider this as "compliance"  as a term.   Can data access be revoked - what happens?  Thought experiment.
      * Can someone ask for their data be removed.  Is there anything data that may be uniquely identifiable.   Differential privacy.   May be difficult to remove.    "Unique Identifiable Information" - best privacy practices.  "K-annonaminity" - taking data out doesn't seem actionable.   ?  How can we describe this. 
      * Identify applicable "Compliance"/"Standards"...  PII would have GDPR constraints.
      * Type of information, and what regulations may apply. 
      * Listing standards & types.
      * Consent - documenting it is still problematic.   Consent and right to use.    Not really covered under standards and regulations.
      * Jean went through ice cream sales and murder rate.
      * Noise - just listing what could be present - TEXT Field Description
      * Sensor - what hardware did you use and was it calibrated.
      * Relevant standards - Text field - optional
      * Context can be handled by relevant standards.
      * Sensitive Personal Information - may imply relevent standards.   But if relevent don't exist.   Yes, NONE, NOASSERTIONS
      * Privatization Method:  Declare or presense - should it be anonimization.   De-identification? 
