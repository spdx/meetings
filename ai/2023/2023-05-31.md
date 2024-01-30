## SPDX AI Team Minutes, May 31, 2023
## Attendees
* Gopi Krishnan Rajbahadur
*Jay White (Microsoft)
* Kate Stewart
* Will Armiros (protect.ai)
* Faisal Khan (protect.ai)
* Sanket Naik (Palosade)
* Sarah Evans (Dell)
* Jonathan Spring
* Badar Ahmed (protect.ai)
* Nick Schifano
* Dmitry Raidan
* Karen Bennet (IEEE)

## Agenda
* PR for relationships:  https://github.com/spdx/spdx-3-model/pull/358
* Overview Slides - https://docs.google.com/presentation/d/1Je3ZqP6VKiHkVQ-NTKjDHJFvyeW8HiUOJcn1irn7DK0/edit?usp=sharing
* Additional feedback from Protect AI on generating AI + Data BoMs (Will + Faisal + Badar)

## Notes
* Intro from Sarah
* Additional Relationships?   
  * + 1 on the PR #358 from Gopi & Karen
* SBOM update when handling CVE (Possibly see also On managing vulnerabilities in AI/ML systems https://dl.acm.org/doi/fullHtml/10.1145/3442167.3442177)
  * AI Incident not handling security vulns
  * Detection bypass - not handled by CVE IDs...; however a lot of ML flaws surfaced by Adversarial ML are mis-categorizations -- which, in security jargon, are probably most similar to detection bypass, and so we might not expect them to get CVE IDs.
  * Link: 
* Vulnerabilities in AI - want to make sure can access,  as well as refer to n VEX

* Karen working on SBOM_Model_GPT4ALL
* GCC willing to fill in some of this,  should follow up

* https://github.com/pytorch/data/pull/330 - to what extent

* ProtectAI - Feedback on programatically generate trained models SBOMs.
  * some progress on SPDX tools repo.   Implementing v3;  on separate branch
  * Will using to create simple BOMs. 
  * Pieces of feedback - on spec itself & python libraries (been very helpful)
  * Help with both and serialization.
  * Using updated V3 tools.   
  * Bigger things - File specificaiton 
     * https://github.com/spdx/spdx-3-model/blob/main/model/Software/Classes/File.md
     * Dataset is several files. 
     * Each file class doesn't have download attribute.
     * Dataset composed of several files. ** Support case. 
     * JSON Serialization - relationships - SPDX document - document serialized together.   Serialize each element.
     * Simple sample code.  -- put in issues. 
* Software Purpose
   * Should some machine learning/ai model in  https://github.com/spdx/spdx-3-model/blob/2d8083040b14212f88dc68bfbd94a6ff9022a92e/model/Software/Vocabularies/SoftwarePurpose.md   - Adding in. 
   
AI: Kate to point Karen & Gopi at where to record minutes.   Karen & Gopi to put in the meeting PRs. 
