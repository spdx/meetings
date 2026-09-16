# SPDX Cryptography Meeting 2026-05-06

###### tags: `ToDo` `Question` `Agreed`

:::info
- **Where:** Remote through [Jitsi](https://meet.jit.si/SPDXCryptoMeeting)
- **When:** Every Wednesday at 15:00 UTC for 30 minutes
- References:
   - Past [MoMs](https://github.com/spdx/meetings/tree/main/cryptography)
   - SPDX Cryptogrphic Algorithms [list](https://github.com/spdx/cryptographic-algorithm-list)
- Approved: 2026-05-13

---

## Attendees

* [ ] Bob Martin
* [x] Alfred Strauch
* [x] Steven Carbno
* [x] Agustín Benito Bethencourt
* [ ] Quique Goñiz
* [x] Mahshid Izady


## Agenda

1. Approval MoM that took place on 2026-04-29
2. News
3. gost family and Magma algorithm
4. Ids conventions
5. What's next?

:::

## MoM

### Approval MoM that took place on 2026-04-29

* Please find the [MoM](https://hackmd.io/S6nqFJApQnChP2YpkqrHPw)

* [x] Approved unanimously 

### News

#### New Issues and PRs
   
* Issue description corresponding to Composite algorithms is now completed. Please check it. [Issue#74](https://github.com/spdx/cryptographic-algorithm-list/issues/74)
* New PR: moving the documents to the /docs folder [PR#75](https://github.com/spdx/cryptographic-algorithm-list/pull/75)
   * Merged during the meeting
* There are conflicts to be solved on [PR#60](https://github.com/spdx/cryptographic-algorithm-list/pull/60) `ToDo`

#### Other news

* OpenChain - SPDX Cryptography Group relation with CBOM
   * Both groups need to attend to each other meetings so each group understand what they are up to. Then we come together to find a collaboration strategy. Mahshid will act as hub to make this happen.
   * This relation came up also on the SPDX Outreach Group
* During our next meeting, Quique Goñiz from SCANOSS, will present how they consume the information on CycloneDX and SPDX CryptAlg in their crypto detection solution
   * Check the strategy they are working on: [article](https://scanoss.com/standardising-crypto-scanosss-open-data-journey/)
* Agustin will look for a second engineer who can lead the release technical procedures and deployments. Jeronimo cannot lead the effort. He joined a new company and has not enough time to lead.

### gost family and Magma algorithm

* [PR#63](https://github.com/spdx/cryptographic-algorithm-list/pull/63) has been closed to concentrate all the changes corresponding to Magma in [PR#64](https://github.com/spdx/cryptographic-algorithm-list/pull/64)
   * Call for review
   * Approved during the meeting
* The [Issue#65](https://github.com/spdx/cryptographic-algorithm-list/issues/65) where we are tracking progress with the gost algorithm family, has been updated accordingly
* Next step: add the predecessor to Magma to our list

### Ids conventions

One of the points made by Karsten in his analysis are related to inconsistencies in the Ids. Check [his document](https://github.com/org-metaeffekt/metaeffekt-cryptography/blob/main/cryptographic-registry-inconsistencies.md). Our ID property description intuitively follows to a great extend what was done at the license list:
* lower case
* dash instead of space or underscore
   * Minimise their usage

But they are ot written in the properties description. This can be extended to all the properties. how do we face this?
* There is no convention for Ids. We need to describe the ID better. `ToDo`
* Do we describing as recommendation or mandatory? 
   * Steven propose to state it as recommendation.
* We want no spaces due to machine reading. Let's confirm this.
   * Let's ask Gary, Alexios... Good question for Quique G. for next meeting.
* ASCII vs Unicode
   * Do we restrict it to ASCII, like the license ids? 
      * Steven suggests to restrict it to ASCII 
* What about the period "."? 

### What's next?

We have 3 workstreams open:
1. Release toolchain and documents
2. List Structure based on Karsten proposal
    1. PQC
    2. IDs
3. Parameters definition: mode

We would like to finish these 3 points before releasing

Which one we prioritise?
1. Release toolchain and documents
2. Parameters definition: mode

these two can be done in parallel

3. PQC

