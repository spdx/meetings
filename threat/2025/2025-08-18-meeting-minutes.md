# SPDX Threats and Controls Team Meeting 2025-08-18

## Attendees

- Karsten Klein
- Steven Carbno
- Alfred Strauch

## Agenda

- Definitions, Definition of Scope
- Outline Objectives
- Naming
- Constitution of group

## Notes

### Concepts to cover

Attacks Patterns: https://capec.mitre.org/about/new_to_capec.html
ICS CAPECs: https://capec.mitre.org/data/definitions/703.html
Mitre Att@ack: https://attack.mitre.org/
Cybersecurity countermeasures: https://d3fend.mitre.org/
Using specific ontologies

### Terms to be Defined / Refined

| Term           | Definition                                                                                                                                                                                                                                                                                                                                                                                                                                                        | Comments                     |
|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------|
| Threat         | A threat is an abstract concept of a potential danger or origin of damage. In security, threats are used to describe scenarios where an adversary attempts to compromise a system and exploit protected resources." Source: metaeffekt                                                                                                                                                                                                                            | Safety uses the term hazard. |
| Threat Model   | "Threat modeling in security is a structured process of identifying, analyzing, and mitigating potential threats to a system, application, or organization" Source: Gemini                                                                                                                                                                                                                                                                                        |                              |
| Vulnerability  | "A weakness in the computational logic (e.g., code) found in software and hardware components that, when exploited, results in a negative impact to confidentiality, integrity, or availability." Source: NVD                                                                                                                                                                                                                                                     |                              |                                                                                                                                                                                                              |          |
| Weakness       | "In security, a weakness is a flaw or vulnerability in a system, process, or design that could be exploited by an attacker to cause harm or compromise security. It represents a potential point of failure that could be leveraged to bypass security measures." Source: Gemini                                                                                                                                                                                  |                              |
| Attack Vector  | "In cybersecurity, an attack vector is the specific method or path a cyber attacker uses to gain unauthorized access to a system or network, ultimately exploiting vulnerabilities to cause harm or steal information." Source: Gemini                                                                                                                                                                                                                            |                              |
| Attack Path    | See attack vector.                                                                                                                                                                                                                                                                                                                                                                                                                                                |                              |
| Attack Pattern | "In cybersecurity, an attack pattern is a structured, repeatable method used by attackers to exploit vulnerabilities in systems, applications, or networks. It represents a blueprint of how an attacker might approach and carry out an attack to achieve malicious objectives like unauthorized access or data breaches. Attack patterns help security teams understand, categorize, and mitigate threats by analyzing common attack behaviors." Source: Gemini |                              |

### Objectives

* Proposals
  * Allow to enrich SPDX documents (containing vulnerabilities) with additional information on
    * Threat-related data (CWE, CAPECs, ICS CAPECs)
    * Threat-analysis results (countermeasures/controls)
  * Allow to define a threat model in an SPDX document
  * Allow to (mostly) lossless convert SPDX 3.y documents to CycloneDx 2.x

### References

#### CycloneDx

* CycloneDx Threat Modeling WG 2025-07-09: https://www.youtube.com/watch?v=Zo8e7tTfbMg
* https://github.com/CycloneDX/specification/compare/master...2.0-dev-threatmodeling#diff-7d330e7323b2020d5cc2ac30e1e3b492ce11259dd02400832c4496e832cb0303

#### OWASP

* https://owasp.org/www-community/Threat_Modeling
* https://owasp.org/www-community/Threat_Modeling_Process
* https://cheatsheetseries.owasp.org/cheatsheets/Threat_Modeling_Cheat_Sheet.html

#### Other

* https://www.threatmodelingmanifesto.org/
* https://github.com/hysnsec/awesome-threat-modelling
* https://d3fend.mitre.org/

## To Do List

* continue defining context and scope 

## Agenda Item Proposals

* none
