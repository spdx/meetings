# SPDX Cryptography Meeting 2026-02-25

###### tags: `ToDo` `Question` `Agreed`

:::info
- **Where:** Remote through [Jitsi](https://meet.jit.si/SPDXCryptoMeeting)
- **When:** Every Wednesday at 15:00 UTC for 30 minutes
- References:
   - Past [MoMs](https://github.com/spdx/meetings/tree/main/cryptography)
   - SPDX Cryptogrphic Algorithms [list](https://github.com/spdx/cryptographic-algorithm-list)
- Approved: 2026-03-04

---

## Attendees

* [ ] Bob Martin
* [x] Alfred Strauch
* [x] Steven Carbno
* [x] Agustín Benito Bethencourt
* [ ] Quique Goñiz
* [x] Jason Smith


## Agenda

1. Approval MoM that took place on 2026-02-18
2. News
3. Release policy
4. Attributes to properties: presence and cardinality

:::

## MoM

### Approval MoM that took place on 2026-02-18

* Please find the [MoM](https://hackmd.io/@toscalix/Skv8YrQubx)

* [x] Approved unanimously 

### News

* Intro from Jason Smith
* Jerónimo Ortiz, former SCANOSS DevOps engineer, has agreed to help us with the technical aspects of the website
* New [blog post](https://toscalix.com/2026/02/24/spdx-cryptographic-algorithm-list-february-2026-update/) - non-official 2026Q1 report published by Agustín
   * There is a [new issue](https://github.com/spdx/cryptographic-algorithm-list/issues/54) to track awareness actions

### Release policy

New version of the [release policy draft](https://github.com/spdx/cryptographic-algorithm-list/issues/52#issuecomment-3920996790)
* Added some of the conclusion from the previous meeting
   * We do not adopt the concept of Release Manager
   * Skipping a release cycle is a "no-action" event
   * New diminutive for the list
* Not included yet: agreement related to mailing lists
* New sections
   * Roles and responsibilities
   * Inclusion and Removal of Cryptographic Algorithms

Is there consensus in the draft for now? `Question`

## Attributes to properties: presence and cardinality

Following the agreement from the last meeting, [an issue](https://github.com/spdx/cryptographic-algorithm-list/issues/55) has been created the define the attributes presence and cardinality on each property

Is the description accurate? `Question`
* No
* Discussion about how we can simplify it and make it machine-readable.
* Adapted the issue.

Is the description  of the issue accurate now? `Question`

We reached consensus `Agreed`

Next step: create the PR `ToDo`
