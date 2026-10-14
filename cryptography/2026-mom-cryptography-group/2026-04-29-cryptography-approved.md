# SPDX Cryptography Meeting 2026-04-29

###### tags: `ToDo` `Question` `Agreed`

:::info
- **Where:** Remote through [Jitsi](https://meet.jit.si/SPDXCryptoMeeting)
- **When:** Every Wednesday at 15:00 UTC for 30 minutes
- References:
   - Past [MoMs](https://github.com/spdx/meetings/tree/main/cryptography)
   - SPDX Cryptogrphic Algorithms [list](https://github.com/spdx/cryptographic-algorithm-list)
- Approved: 2026-05-06

---

## Attendees

* [x] Bob Martin
* [x] Alfred Strauch
* [x] Steven Carbno
* [x] Agustín Benito Bethencourt
* [ ] Quique Goñiz
* [x] Mashid Izady
* [x] Jean Camp
* [ ] Karsten Klein


## Agenda

1. Approval MoM that took place on 2026-04-22
2. cryptoClass and cryptoSubClass restructuring
3. Other topics

:::

## MoM

### Approval MoM that took place on 2026-04-22

* Please find the [MoM](https://hackmd.io/jfA3WZAWTASlIhiRaULZcA)
   * There is a pending topic from Bob that Agustin did not record `ToDo`. We will record it in coming meeting.

* [x] Approved unanimously 

### News

#### New issues related to the List re-structuring

* New issue related with a potential cryptoSubClass values redundancy [Issue #70](https://github.com/spdx/cryptographic-algorithm-list/issues/70)
* New issue to assign new values to the cryptoSubClass property associated to the new cryptoClass values: [Issue#72](https://github.com/spdx/cryptographic-algorithm-list/issues/72)
* New issue to track the PQC property description [Issue 73](https://github.com/spdx/cryptographic-algorithm-list/issues/73)
* New issue (WIP) to track the composite category, that is, algoriothms that are compositions of tow or more primitives: [Issue#74](https://github.com/spdx/cryptographic-algorithm-list/issues/74)

#### Pending PRs

* There are several PRs pending for review:
   * Simple-quick reviews: `ToDo`
      * [PR#63](https://github.com/spdx/cryptographic-algorithm-list/pull/63)
         * There are comments to adress
      * [PR#64](https://github.com/spdx/cryptographic-algorithm-list/pull/64)
        * There are comments to adress.
        * I was late; but here is what I found on Magma: Magma is the modern name for the Russian block cipher GOST 28147-89, formally renamed in GOST R 34.12-2015 as the 64-bit Magma cipher. Quick facts:
            - 64-bit block, 256-bit key, 32-round Feistel structure
            - The 2015 standard fixed the previously implementation-defined S-boxes (the original GOST 28147-89 left S-boxes to the user, which historically caused interop issues and weakened security)
            - Companion to Kuznyechik (Grasshopper, GOST R 34.12-2015), the 128-bit successor block cipher
            - Standardised in IETF: RFC 8891 (Magma block cipher), RFC 5830 (legacy GOST 28147-89)
            - Mandatory in Russian government / financial systems 
            * These ones require more effort: `ToDo`
        * [PR#62](https://github.com/spdx/cryptographic-algorithm-list/pull/62)
        * [PR#60](https://github.com/spdx/cryptographic-algorithm-list/pull/60)

#### Other topics

* Some additional algorithms candidates have been added to the [issue#43](https://github.com/spdx/cryptographic-algorithm-list/issues/43) for tracking
* Agustin would like to invite to this meeting to a SCANOSS engineer so they provide a demo of their crypto algorithm detection solution, using open source software, so we learn about how downstream tools can potentially consume our List. What do you think? Could this be useful?

### cryptoClass and cryptoSubClass restructuring

* The proposal for cryptoClass, based on the [consensus reached last week](https://hackmd.io/jfA3WZAWTASlIhiRaULZcA?both=&stext=665%3A11%3A0%3A1777462274%3APqAXJ6) is
   * [cryptoClass proposal](https://github.com/spdx/cryptographic-algorithm-list/issues/68#issuecomment-4342489475)
* Based on the above proposal, the proposal for adapting cryptoSubClass is [subCryptoClass proposal](https://github.com/spdx/cryptographic-algorithm-list/issues/69#issuecomment-4342904379)

Is there any problem with these two proposals? `Question`

This PR is based on both proposals, including the affected algorithms: [PR#71](https://github.com/spdx/cryptographic-algorithm-list/pull/71)
* Call for review `ToDo`

### Other topics

* We are recuiting cryptographers for this group
* Consensus on coordination with OpenChain required, especially the telco group
* Next step would be to push a proposal for PQC 
   * Maybe we can invite the people behind this initiative: https://datatracker.ietf.org/doc/draft-dev-xipher-cbom-extension/ 
   * Check Karsten reference as starting point https://github.com/org-metaeffekt/metaeffekt-cryptography/blob/main/cryptographic-algorithms.md
