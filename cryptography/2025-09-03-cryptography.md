# SPDX Cryptography Meeting 2025-09-03

###### tags: `ToDo` `Question` `Agreed`

:::info
- **Where:** Remote through [Jitsi](https://meet.jit.si/SPDXCryptoMeeting)
- **When:** Every Wednesday at 14:00 UTC for 30 minutes
- References:
   - Past [MoMs](https://github.com/spdx/meetings/tree/main/cryptography)
   - Crypto algorithms [list](https://github.com/spdx/crypto-algorithms)

## Attendees

* [ ] Bob Martin
* [x] Alfred Strauch
* [x] Steven Carbno
* [x] Agustín Benito Bethencourt
* [ ] Quique Goñiz


## Agenda

1. News
2. Eliptic Curve
3. OID
4. AOB

:::

## MoM

### News

* Our list has been archived at SwH
* Matias D'aloia, from SCANOSS, explained the company's strategy arond cryptographic algorithms, including their effort put into this SPDX Crypto Algorithms List. The  slide deck will be uploaded as soon as Matias comes back from vacation.
   * [Link](https://osseu2025.sched.com/event/25Vp2/know-your-crypto-standardizing-and-detecting-crypto-algorithms-the-open-source-way-matias-daloia-scanoss) to the talk to tracj video and deck
* The ticket [New Property OID](https://github.com/spdx/crypto-algorithms/issues/20) has been described. Please review
* The ticket [New Property: eliptive curve](https://github.com/spdx/crypto-algorithms/issues/21) is WIP

### Eliptic Curve

* Do we need to provide the parameters for the elliptic curve algorithms? `Question`
   * What is CycloneDX doing?

### OID

* We can restrict our work to the ones where there is an standardization entity that has published the identifier
* We can add the high level OID for the algorithm so we do not need to add the OID for each modification (key) of the algorithm
* Make a PR with one or two algorithms including OID so the group can evaluate it `ToDo`

### AOB

* Agustin cannot assign labels to tickets. It requires a triage role
   * Ask Gary or Kate about permissions related with the labels (triage role?)
* Make a PR with one algorithm in relation with [ticket 16](https://github.com/spdx/crypto-algorithms/issues/16) keeping the PR wip so the group can evaluate it. `ToDo`
