# SPDX Threats and Controls Team Meeting 2025-09-15

## Attendees

- Karsten Klein
- Alfred Strauch
- Steven Carbno
- Greg Shue

## Agenda

- Revisit Notes/Todos from last meeting; fill in details
   - Risk Analysis vs Threat Analysis
   - Hazard (safety) vs Threat (security)
   - Needs / Identifying the needs
   - Needs +1 additional level of requirements
   - Users to stakeholders; stakeholders include all potential users

## Notes

Weakness - Vulnerability - Exploit (considering a leveled approach)

### Most important Definitions

#### Threat

*A threat is the potential of a negative circumstance or event.* 

Discussion / Resources:
- This generic definition is regarded in full alignment with [CNSSI 4009] and [NIST SP 800-30 Rev 1]
- The CNSSI glossary limits the definition threat by listing affected elements and adverse outcomes. 
  This is not necessary.
- CNSSI 4009 - Threat:
  Any circumstance or event with the potential to adversely impact organizational operations (including mission,
  functions, image, or reputation), organizational assets, individuals, other organizations, or the Nation through an
  information system via unauthorized access, destruction, disclosure, or modification of information, and/or denial
  of service.
- SEVOCAB - Threat:
  (1) state of the system or system environment which can lead to adverse effects (ISO/IEC/IEEE 24765a:2011)
  (2) risk that would have a negative effect on one or more project objectives (A Guide to the Project Management Body 
  of Knowledge (PMBOK(R) Guide) -- Seventh Edition)

#### Impact

*Impact is the resulting damage or consequence of a negative circumstance or event.*

Discussion
- While a threat refers only to potential of a negative circumstance of event the impact describes the consequence.

#### Likelihood

The likelihood of a negative circumstance or event is the probability or certainty of a threat manifestation.

#### Risk

*Risk is a measure for an identified threat or hazard. Risk is a function of Impact and Likelihood (R = I x L).*

Discussion:
- highest impact and likelihood implies highest risk
- when talking about risk we often mean threat
- Risk assessment implies threat assessment
- CNSSI 4009 - Risk:
  A measure of the extent to which an entity is threatened by a potential circumstance or event, and typically a 
  function of: (i) the adverse impacts that would arise if the circumstance or event occurs; and (ii) the likelihood of 
  occurrence.
- SEVOCAB - Risk:
  (1) effect of uncertainty on objectives (ISO/IEC 19770-1:2017 Information technology -- IT asset management -- Part 1: IT asset management systems--Requirements, 3.48) (A Guide to the Project Management Body of Knowledge (PMBOK(R) Guide) -- Seventh Edition, 3.44) (ISO/IEC/IEEE 12207:2017 Systems and software engineering--Software life cycle processes, 3.1.47) (ISO/IEC/IEEE 16085:2021 Systems and software engineering--Life cycle processes--Risk management, 3.5) (ISO/IEC/IEEE 15288:2023 Systems and software engineering--System life cycle processes, 3.39)
  (2) combination of the likelihood of occurrence and the consequences of a given future undesirable event (IEEE 1012-2024 IEEE Standard for System, Software, and Hardware Verification and Validation, 3.1)
  (3) combination of the likelihood of an abnormal event or failure and the consequences of that event or failure to a system's components, operators, users, or environment (IEEE 1012-2024 IEEE Standard for System, Software, and Hardware Verification and Validation, 3.1)
  (4) combination of the probability of occurrence of harm and the severity of that harm (IEC/IEEE 82079-1:2019 Preparation of information for use (instructions for use) of products: Part 1: Principles and general requirements, 3.32)
  Note: Risk is often expressed in terms of a combination of the consequences of an event and the associated likelihood of occurrence. The probability of occurrence includes the exposure to a hazardous situation, the occurrence of a hazardous event, and the possibility to avoid or limit the harm. See Also: opportunity


Who or what could cause damage or harm? 


#### Hazard

A hazard is a potential of a negative circumstance or event causing injury or harm to humans or other living creatures.

Discussion:
- Safety prioritizes harm or injury to humans or animals; hazards in safety are threats in cybersecurity
- Gemini: In summary, a hazard is typically a static or inherent condition with the potential for harm, while a threat 
  is an active source or agent that could cause an unwanted event. The key difference lies in the nature of the 
  potential danger — one is an inherent property, the other is an active force.
- A hazard is a specific, but passive threat; a cybersecurity threat is a specific active threat
- A hazard is a threat imposing an impact on humans health and integrity
- SEVOCAB - Hazard: 
  (1) intrinsic property or condition that has the potential to cause harm or damage (IEEE 1012-2024 IEEE Standard for 
  System, Software, and Hardware Verification and Validation, 3.1.11)
  (2) source of potential harm or a situation with a potential for harm in terms of human injury; damage to health, 
  property, or the environment; or some combination of these (IEEE 1012-2024 IEEE Standard for System, Software, and 
  Hardware Verification and Validation, 3.1.11)
  (3) source of potential harm (ISO/IEC/IEEE 26513:2017 Systems and software engineering -- Requirements for testers and 
  reviewers of information for users, 3.17) 
  (4) potential source of harm (IEC/IEEE 82079-1:2019 Preparation of information for use (instructions for use) of 
  products: Part 1: Principles and general requirements, 3.15) (IEEE 7009-2024, Fail-Safe Design of Autonomous and Semi-
  Autonomous Systems, 3.1)
  (5) source or situation with a potential for harm in terms of human injury or ill health (both short and long term), 
  damage to property, damage to the environment, or a combination of these (IEEE 7000:2021, IEEE Standard Model Process 
  for Addressing Ethical Concerns during System Design, 3.1)

## Agenda Item Proposals

- Further deep-dive on risk assessment and risk assessment processes

## References

https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-30r1.pdf
https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-2e2025.pdf
https://doi.org/10.6028/NIST.CSWP.46
https://nsarchive.gwu.edu/document/22385-document-08-committee-national-security
https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-30r1.pdf
https://pascal.computer.org/sev_display/index.action

SEVOCAB-related statement: "Copyright©, 2025, IEEE. Used by permission."
The definitions from CNSSI 4009 are used from NIST SPs.

## TODOs:

- Extend definitions by weakness, vulnerability and exploit
- Extend definitions by asset (compare with CRA-related content)