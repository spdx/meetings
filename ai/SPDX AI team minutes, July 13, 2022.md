## SPDX AI team minutes, July 13, 2022
## Attendees:
  * Kate Stewart
  * Derek Kruszewski
  * Gopi Krishnan Rajbahadur
  * Dick Brooks
  * L Jean Camp
  * Mehdi Entezari
  * Chris Shenefiel

## Agenda
  * Introduce new participants 
  
## Notes
* Introduction of new participants
  * Mehdi Entezari (Unisys)
  * Chris Shenenfield  (Cisco)
  
* Review of the 1.0 draft
    * Derek Trying to tease difference between  AI Application & AI Model. (from https://docs.google.com/document/d/1M-JNBtNvqxg51AjP8G5yJwzhtzv5RW-RyDxiAIDQloY/edit and https://docs.google.com/presentation/d/19sKlG31wwQDVM4heaekKDvFA94ydWGY9lVHmdWvckmA/edit#slide=id.gf47cb0d937_0_0)
    * Possibly AI context only applies to packages,  some only relevant to files?
    * Datafiles - refering to zip file?  
    * But what about descriptive data sets?  
    * Thought experiment
        * AI Context - applies to packages;   AI Model - appies to file  so "AI Profile" encompasses both elements
        * Dataset Profile - abstract that applies to group of files (aka package).
    * If its a publicly available pre-trained model - how have it's own representation?
    * Would you ever refer to a data set abstractly?   Yes, where it is not included in - like multi-terabyte database.   This many samples, etc. are properties.   Dataset profile, even though don't make it available.
    * Describe datasets abstractly vs. models abstractly. 
    * Thinking about purpose - have something that can be attest is compliant.   Think about fields - PII example.  Clear source of responsibility.   Want to know if data was compromized (poisoned) need to retrain.
    * Higher level goal of trustworthy AI.  Pointer to attestation and claims of data. 
    * Should AI model be included as a hash at a point in time.    Over time, will change,  so hash.
    * Attestation of provability of data sources used.
    * Datasets exist during training - timestamp and store - and provide attestation of this info. 
    * Key - we can only ask for traceability, not reproducibility.   Assertions at points of time about PII as examples with synthetic data sets.
