# SPDX Threats and Controls Team Meeting 2025-09-29

## Attendees

- Greg Shue
- Nicole Pappler
- Steven Carbno
- Alfred Strauch
- Karsten Klein

## Agenda

- Continue definitions:
  - Extend definitions by weakness, vulnerability and exploit
  - Extend definitions by asset (compare with CRA-related content)
  - (Extend definitions on who or what could cause damage or harm?)
  - Threat Source / Threat Agent / Threat Actor / Threat Scenario; see NIST
    - see materials below
- Options
    - Collect inputs for outstanding definitions
    - Deep dive into Risk Assessment
        - https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-30r1.pdf
        - ISO 31000 / ISO 27005 / ISA 62443-3-2

## References

- https://www.youtube.com/watch?v=qS0FY6wZs9Mm - Business of Cyber Series - Deep Dive into ISA/IEC 62443 3-2

## Notes

- 

### Weakness

https://csrc.nist.gov/glossary/term/weakness:

A condition in a software, firmware, hardware, or service component that, under certain circumstances, could contribute 
to the introduction of vulnerabilities.
Sources: NIST IR 8517 from MITRE CWE

In cybersecurity, weakness is a general term for a shortcoming, flaw, or deficiency in a system's design, 
implementation, or procedures that could potentially lead to a security problem.
It is often used in a broader context than a vulnerability.
A Weakness is the root cause or underlying deficiency (e.g., failing to enforce strong password policies or using a 
known-insecure encryption algorithm).
A Vulnerability is a specific instance of a weakness that is already exploitable by a threat (e.g., a specific unpatched 
software bug that allows an attacker to take control).
Source: Gemini

In short: A vulnerability is an exploitable weakness.

Vulnerability: "A weakness in the computational logic (e.g., code) found in software and hardware components that, when 
exploited, results in a negative impact to confidentiality, integrity, or availability."
Source: NVD


### Vulnerability

A weakness that can be exploited or triggered to produce an adverse effect.
Sources: NIST SP 800-160v1r1

A weakness in system security procedures, system design, implementation, internal controls, etc., that could be 
exploited to violate the system security policy. 
Sources: NISTIR 4734 under Vulnerability

### Exploit

An exploit is a method or piece of code that takes advantage of vulnerabilities in software, applications, networks, 
operating systems, or hardware, typically for malicious purposes.
Source: Wikipedia




### Materials

From SEVOCAB:

asset. (1) item, thing, or entity that has potential or actual value to an organization (ISO/IEC 19770-5:2015 
Information technology--IT asset management--Overview and vocabulary, 3.2) (2) item that has been designed for use in 
multiple contexts (IEEE 1012-2024 IEEE Standard for System, Software, and Hardware Verification and Validation, 3.1.3) 
(3) item, such as design, specifications, source code, documentation, test suites, or manual procedures, that has been 
designed for use in multiple contexts (IEEE 1012-2024 IEEE Standard for System, Software, and Hardware Verification and 
Validation, 3.1) Example: requirements documents, source code modules, measurement definitions Note: Physical assets 
usually refer to equipment, inventory and properties owned by the organization. Physical assets are the opposite of 
intangible assets, which are non-physical assets, such as leases, brands, digital assets, use rights, licenses, 
intellectual property rights, reputation or agreements. A grouping of assets referred to as an asset system can also be 
considered as an asset. 

I found this list and associated descriptions at Know Your Enemy: Types of cybersecurity threat actors.

Nation-State Actors
Cybercriminals
Hacktivists
Insider Threats
Thrill Seekers and Script Kiddies 

Lookup:
Structured Threat Information Expression (STIX™)


There is a publicly available conference paper about the MoRa:
https://www.researchgate.net/publication/336413410_Modeling_Security_Risk_Assessments

