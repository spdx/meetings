# SPDX Cryptography Meeting 2026-04-01

###### tags: `ToDo` `Question` `Agreed`

:::info
- **Where:** Remote through [Jitsi](https://meet.jit.si/SPDXCryptoMeeting)
- **When:** Every Wednesday at 15:00 UTC for 30 minutes
- References:
   - Past [MoMs](https://github.com/spdx/meetings/tree/main/cryptography)
   - SPDX Cryptogrphic Algorithms [list](https://github.com/spdx/cryptographic-algorithm-list)
- Approved: 2026-04-08

---

## Attendees

* [x] Bob Martin
* [x] Alfred Strauch
* [x] Steven Carbno
* [x] Agustín Benito Bethencourt
* [ ] Quique Goñiz


## Agenda

1. Approval MoM that took place on 2026-03-18
2. Discussion about the concept of deprecation
3. News
4. CONTRIBUTING.md
5. Release Process
6. Criteria for the Cryptography Group to approve/reject new algorithms or removals
7. gost
8. Second batch of references
9. Request to the security profile on how they will use the CryptAlg List
10. Karsten provided information about algorithms

:::

## MoM

### Approval MoM that took place on 2025-03-18

* Please find the [MoM](https://hackmd.io/UA1kylyjR5qvaRyDd339Ag)

* [x] Approved unanimously 

### Discussion about the concept of deprecation

During a meeting held on 2026-03-25, the only topic discussed was how to adress the concept of deprecation of an algorithm. The discussion was triggered by:
* The submission of [PR#60](https://github.com/spdx/cryptographic-algorithm-list/pull/60)
* The creation of the [Issue#61](https://github.com/spdx/cryptographic-algorithm-list/issues/61)

#### Deprecation concept discussion

Discussion about the concept of deprecation applied to the list. The current content created by agustin consider the concept of deprecation but the use case bring several challenges that we cannot solved under the Group right now. One of them is that we have no way to track relations among algorithms.

The general consensus is that we remove the concept of deprecation for now and just add as criteria de use case in which an algorithm change its name. `Agreed`

Add as information in CONTRIBUTING.md submitters add to the github issue containing the new algorithm inclusion proposal all the info required for the Cryptography Group to get context and to evaluate the impact on the List out of any decision of a standardization body afecting the corresponding algorithm and any other affected. An example is the case in which a new algorithm is considered standard and the former one is deprecated. The proposal should bring references to both, so we make sure that both of them are approetly reflected on the List. `Agreed`

Actions:
* Remove the concept of deprecation from section 6 of the release process `ToDo`
* Remove the concept of deprecation from the key words of the release process `ToDo`
* Remove it also from the addition/removal criteria document `ToDo`
* Add a reference to the use case of submissions to the list of new algorithms or changes due to the deprecation by a sptanrdization body of an algorithm `ToDo`

### News

* New [PR#60](https://github.com/spdx/cryptographic-algorithm-list/pull/60): adding to CONTRIBUTING.md the process to add or remove algorithms 
* New [PR#62](https://github.com/spdx/cryptographic-algorithm-list/pull/62): SPDX CryptAlg release process 
    * Section 6 reformulated to remove the concept of deprecation
    * Key terms: deprecation and generation removed from key terms
    * Sections 12.4 and 13.3 adapted to soften the requirement to open an issue before a PR. In trivial cases we should go directly to PRs
    * Moved RELEASE-HISTORY.md and CHANGELOG.md from the Key Terms to the Reference section
    * Added links to every entry in the 14.2 section
    * Some minor changes in the Key Terms (14.1) section
* The [Issue#56](https://github.com/spdx/cryptographic-algorithm-list/issues/56) has been updated to reflect the current status of the documentation that should be ready for the publishing of the list on the website 
    * Agustin sent a status email to Gary about the work on the website/deployment
* Issue including the proposal: new-cryptographic-algorithm-inclusion-removal-criteria.md [Issue#61](https://github.com/spdx/cryptographic-algorithm-list/issues/61)
* New algorithm missing in the list: [ffdh](https://github.com/spdx/cryptographic-algorithm-list/issues/43#issuecomment-4170159072)

### CONTRIBUTING.md

* Call for PR review [PR#60](https://github.com/spdx/cryptographic-algorithm-list/pull/60)
    * Submission, review and approval process of new algorithms
* id should be lowercase. Add this to the property description `ToDo`

### Release Process

* Call for PR review [PR#62](https://github.com/spdx/cryptographic-algorithm-list/pull/62)

### Criteria for the Cryptography Group to approve/reject new algorithms or removals

* Discussion of the proposal for the "Cryptographic Algorithm Inclusion and Removal Criteria" Check [the current proposal](https://github.com/spdx/cryptographic-algorithm-list/issues/61#issuecomment-4126853975)
    * Ready to create a PR?
        * Before creating a PR, Agustin have to remove the deprecation reference, which is still there `ToDo`

### gost

While looking for references, I realised that the reference we had was out of date for the gost algorithm. Reading the new standardised version, some parameters needed to be add and updated. The result is a new PR
* [PR#63](https://github.com/spdx/cryptographic-algorithm-list/pull/63) `ToDo`

This is another of those cases where, as a result of the action of a standardization body, an algorithm changes their properties. Given that the id has not changed, Agustin did not create a new algorithm

#### Discussion

We need to add all gost algorithms [Issue#65](https://github.com/spdx/cryptographic-algorithm-list/pull/65) `ToDo`

### Second batch of references

* The second batch of references has been completed. [PR#64](https://github.com/spdx/cryptographic-algorithm-list/pull/64) submitted for review

### Request to the security profile on how they will use the CryptAlg List

* Bob request for an example about how the Security profile will use the list. `Question`
    * Steven provides status on the discussions about how to use the CryptAlg List within the Security profile

### Karsten provided information about algorithms

We should strongly consider the work done by Karsten, summarised here https://github.com/org-metaeffekt/metaeffekt-cryptography/blob/main/cryptographic-algorithms.md It has implications of how we structure the algorithms. Check cryptoClass

Check the list of iods he provided. They need validation
