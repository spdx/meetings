# SPDX FuSa Group Meeting - 2023.11.03

## Attendees
* Nicole Pappler
* Karsten Klein
* Kate Stewart
* Maximillian Huber

## Notes
* Karsten introduced self and intrest in how to get safety people interacting better with security.
* Kate flagged https://www.nist.gov/artificial-intelligence/artificial-intelligence-safety-institute to see if there is interest in participating in submitting a letter.   Nicole has interest. 
* Kate provided an overview of progress on hardware BOM efforts.   Starting with physical and extending into virtual and safety needs.
* Karsten introduced discussion of CVSS4 - with "Safety" presence,  and discussion of implications.   Will present more context next meeting.    Kate shared https://www.nisc.go.jp/eng/pdf/cip_policy_2022_eng.pdf also has safety profile considerations.   Nicole clarified that Hazards should also incorporate Controllability, Detectability that is not present in the CVSS4
* Nicole went through draft of the FUSA BOM,  discussion ensued probably be more efficient to do it in JSON so better integration with tools.   (Relationship with design & completness).    Also noted that Hazard and Risk analysis happens at the "System" level, and isn't showing up in our modeling.  62443 controls need to be considered.   Security controls are "just requirements", that need to be addressed. 
* Hazards (from system level) are just information model parts.   Controls are just a checklist would be considered as test.  
* Subtlety of running on framework vs. in production - for evidence.   Where would a security checklist belong.  Safety point of vie - it's deploy.   But runtijme?  maky make snese for Runtime? 
