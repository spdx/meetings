# SPDX Cryptography Meeting 2025-12-03

###### tags: `ToDo` `Question` `Agreed`

:::info
- **Where:** Remote through [Jitsi](https://meet.jit.si/SPDXCryptoMeeting)
- **When:** Every Wednesday at 14:00 UTC for 30 minutes
- References:
   - Past [MoMs](https://github.com/spdx/meetings/tree/main/cryptography)
   - Crypto algorithms [list](https://github.com/spdx/crypto-algorithms)

## Attendees

* [ ] Bob Martin
* [ ] Alfred Strauch
* [x] Steven Carbno
* [x] Agustín Benito Bethencourt
* [ ] Quique Goñiz
* [x] Andrew Vlater
* [x] Dave


## Agenda

1. News
2. New property: reference
3. Discrepancies between SPDX and CycloneDX Ids
4. New candidates to the list

:::

## MoM

### News

* Pinged Alexios to find out what can we do so our PRS get more attention, as discussed in previous meetings.
   * Alexios proposes a way to move forward
   * Who should have merge rights? As long as there is more than one review, and the reviewr is not the creator, we can provide merge rights to Bob, Steven and Agustin
   * Send an answer to Alexios `ToDo`
* Bug detected on the list: Issue [#40](https://github.com/spdx/cryptographic-algorithm-list/issues/40)

### New property: reference

This is the list we have so far of algorithm references [Issue #9](https://github.com/spdx/cryptographic-algorithm-list/issues/9#issuecomment-3553145225)

Next step is to check the correctness of this list. `ToDo`

### Discrepancies between SPDX and CycloneDX Ids

As a result of the work on the property "reference" performed this week, some discrepancies between Cyclone DX IDs and SPDX IDs have been detected. Checl Issue [#41](https://github.com/spdx/cryptographic-algorithm-list/issues/41)

We need to evaluate, discuss and take a decision on each one of these. One of our goals was to keep as much compatibility as possible between our list and Cyclone DX.

* Do we allow alternate names/ids ?
   * Multiple Ids is challenging
* Do we define a way that provides answer to cases like evolutions of algorithms, deprecations...
* We might need to define a criteria for clarifying which ID we will pick in case there is more than one option.
   * Going for the standardised ID as priority could be the way to go

### New candidates to the list

As a result of the work on the property "reference" performed this week, I have listed some algorithms that might be candidates for the SPDX, after a discussion, because there might be some that will not make it.
   * Please check the issue [#43](https://github.com/spdx/cryptographic-algorithm-list/issues/43)

Moving forward, Agustin is defining a process to propose new algorithms to the list, so we consider them one by one on a structured manner, with two goals in mind:
* The process should be lightweight for those proposing the algorithms, so they do not need to learn about the technical details of the list at first
* We minimise the PR review process guaranteeing that, by the time the corresponding PR is created, all the information is there, so the PR is already mature.

Check the dratf of this proposal, that is not fully ready yet for discussion [Issue #42](https://github.com/spdx/cryptographic-algorithm-list/issues/42)

* Can we merge the process on a single ticket? `Question`
   * Use labels to manage the process
   * We can have a sample ticket done by us that we can use as reference
   * Let's use as example one of the algorithms proposed in Issue [#43](https://github.com/spdx/cryptographic-algorithm-list/issues/43)

It is pending the definition of the part of the process related with the content that the PR should include, which was discussed in a previous meeting. `ToDo`
