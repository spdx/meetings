# SPDX Cryptography Meeting 2026-08-04

###### tags: `ToDo` `Question` `Agreed`

:::info
- **Where:** Remote through [Jitsi](https://meet.jit.si/SPDXCryptoMeeting)
- **When:** Every Wednesday at 15:00 UTC for 30 minutes
- References:
   - Past [MoMs](https://github.com/spdx/meetings/tree/main/cryptography)
   - SPDX Cryptogrphic Algorithms [list](https://github.com/spdx/cryptographic-algorithm-list)
- Approved: 2026-08-11

---

## Attendees

* [x] Bob Martin
* [x] Alfred Strauch
* [x] Steven Carbno
* [x] Agustín Benito Bethencourt
* [ ] Quique Goñiz
* [x] HArt Montgomery
* [x] Andreas Schabe
* [x] Aditya Koranga
* [x] KArsten Klein
* [x] Robert Martin 


## Agenda

1. Introduction
2. Discuss the different proposals on PQC
3. Missing cryptoSubClass values

:::

## MoM

### Introduction

* Introduction of the experts who joined today
* Context provided for all the new audience on where are we and where do we need help
    * At different points of the conversation the Cryptography Group Members provide context on different points

### Discuss the different proposals on PQC

* We went through the different approaches described in the proposal [Issue#73](https://github.com/spdx/cryptographic-algorithm-list/issues/73)
* Debate about how any of the proposals can be used: use cases
* There is an idea of using the current cryptoClass and then jump to a single level structure to deal with the PQC based on the mathimatical characteristics
    * Remove the parameters of these algorithms for now
    * NIST does a good job with the high level classification of the PQC algorithm from a math PoV.
    * Suggestion to start with what NIST provides https://csrc.nist.gov/projects/pqc-dig-sig/round-3-additional-signatures 
    * Link to standards: https://csrc.nist.gov/Projects/post-quantum-cryptography

* Conversation about CycloneDX vs SPDX approach to the Cryptology topic
    * Question: did SPDX went over cycloneDX approach before starting?
        * Cryptography Group members: we did
    * cycloneDX went for simplicity but it might be too simplistic.
        * Simple vs simplistic: find the sweet spot as advice to SPDX
*  Vulnerabilities in the PQC seem to be affecting specific algorithms vs entire cryptoSubClass or cryptoClass (pqcClass) 

### Missing cryptoSubClass values

* Short description about the current proposal.
* No time to go over it.
