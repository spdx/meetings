# SPDX Cryptography Meeting 2026-04-15

###### tags: `ToDo` `Question` `Agreed`

:::info
- **Where:** Remote through [Jitsi](https://meet.jit.si/SPDXCryptoMeeting)
- **When:** Every Wednesday at 15:00 UTC for 30 minutes
- References:
   - Past [MoMs](https://github.com/spdx/meetings/tree/main/cryptography)
   - SPDX Cryptogrphic Algorithms [list](https://github.com/spdx/cryptographic-algorithm-list)
- Approved: yyy-mm-dd

---

## Attendees

* [x] Bob Martin
* [x] Alfred Strauch
* [x] Steven Carbno
* [x] Agustín Benito Bethencourt
* [ ] Quique Goñiz
* [x] Karsten Klein


## Agenda

1. Approval MoM that took place on 2026-04-08
2. News
3. cryptoClass parameter reform proposal

:::

## MoM

### Approval MoM that took place on 2026-04-08

* Please find the [MoM](https://hackmd.io/EFNLAxvVRgCZnKSiUD3HwA)

* [x] Approved unanimously 

### News

* New [PR#67](https://github.com/spdx/cryptographic-algorithm-list/pull/67) related with modes
   * This PR is related to [Issue#39](https://github.com/spdx/cryptographic-algorithm-list/issues/39)
* Agustin is behind submitting MoM to the meetings directory due to the need to adress the commont about separate them per year, which will require to ammend some of the current PRs
* The criteria to [add/remove algorithms proposal](https://github.com/spdx/cryptographic-algorithm-list/pull/66) has been reviewed and merge during the meeting

### cryptoClass property reform proposal

* A new issue was created to reflect the outcome of last meeting conversation based on Karsten Klein's proposal 
   * Check [Issue #68](https://github.com/spdx/cryptographic-algorithm-list/issues/68)
* A [new proposal](https://github.com/spdx/cryptographic-algorithm-list/issues/68#issuecomment-4252538099) has been created for cryptoClass property
   * Please evaluate

Discussion
* Do we need a specific cryptoClass for Post-Quantum-Cryptography? `Question`
    * We all agree that we will need to develop on the subCryptoClass
    * We are confortable for now with having Post-Quantum-Cryptography as a cryptoClass `Agreed`
* Are all the Post-Quantum-Cryptography simetric? `Question`
   * No. Confirm! 
* From Karsten, to consider
   * Key Encapsulation
   * Key Agreement
   * Digital Signatures (stateless)
   * Digital Signatures (stateful)
   * PQC Migration and Candidates 

### Parameter mode syntax

Based on the [proposal](https://github.com/spdx/cryptographic-algorithm-list/pull/67) made by Steven, we can see:

* Steven describes the proposal
* Karsten describe use cases to consider for the parameters
   * Use case 1: algorithm identification. Precision
   * Use case 2: algorithm support.
   * Use case 3: lifecycle. Check [this](https://github.com/org-metaeffekt/metaeffekt-cryptography/blob/main/cryptographic-algorithm-status.md)


```
parameters:

* name: keyLength
* type: 
* Summary: 
* Description: 

* name: mode
* Summary:
* Description:
* type:
* value
```

Questions:
* Do we use the same .md file to describe properties and parameters?
   * Same file initially 
* Do we use the same way to describe both?
    * If we can, yes
    * Should we use the same/analogous syntax for parameters and properties?
       * Initially, yes we should. We might not be able at some point
* Should we adopt different names to describe parameters and properties?
   * Initially, no. We would like to keep it as similar as possible (valid in general for all aspects of parameters)



