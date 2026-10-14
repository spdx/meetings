# SPDX Cryptography Meeting 2026-08-11

###### tags: `ToDo` `Question` `Agreed`

:::info
- **Where:** Remote through [Jitsi](https://meet.jit.si/SPDXCryptoMeeting)
- **When:** Every Wednesday at 15:00 UTC for 30 minutes
- References:
   - Past [MoMs](https://github.com/spdx/meetings/tree/main/cryptography)
   - SPDX Cryptogrphic Algorithms [list](https://github.com/spdx/cryptographic-algorithm-list)
- Approved: 2026-08-26

---

## Attendees

* [x] Bob Martin
* [x] Alfred Strauch
* [x] Steven Carbno
* [x] Agustín Benito Bethencourt
* [ ] Quique Goñiz


## Agenda

1. Approval MoM that took place on 2026-08-04 and 2026-07-29
2. PQC Class
3. AOB

:::

## MoM

### Approval MoM that took place on 2026-08-04 and 2026-07-29

* Please find the MoMs:
    * [MoM 2026-07-29](https://hackmd.io/Q3capDNeRvKLdnTWF8iQlQ)
        * [x] Approved unanimously 
    * [MoM 2026-08-04](https://hackmd.io/5QevdZ5nRQaOJnJavg2AWA)
        * [x] Approved unanimously 

### PQC Class

* Steven iteration: https://github.com/spdx/cryptographic-algorithm-list/issues/73#issuecomment-5193137916
* Additional iteration from Agustin: https://github.com/spdx/cryptographic-algorithm-list/issues/73#issuecomment-5267793501

Question 7 of Agustin's iteration:
* Compositions of algorithms that results in PQC algorithm can be declared as composite AND pqcClass. Another approach to deal with composite is adapt the cardinality of pqcClass. `Question`

Process
* Send the proposal to the participants in the previous meeting
* If they have substantial concerns that cannot be addressed offline, we agree on a meeting with them.


### AOB

#### Syntax

* Should the IDs be case sensitive? Discuss this further. It is relevant within the syntaxt discussion `Question`
    * Making the non-case-sensitive might resolv some potential challenges

#### Validation and review

* Validation and review process on relevant decisions. We need a process that involve a second ring of experts, beyond the existing participants
* We need a method to ensure the involvement of experts
* We need two polish a bit the review process for PRs `Agreed`
    * Current: "At least one group member other than the author must approve the pull request before it can be merged. "
    * Proposal: At least one group member **with merge rights** other than the author must approve the pull request before it can be merged. `ToDo`
* Agustin will send a mail to the previous meetings participants. `ToDo`
* Alfred will be in charge in general of the communication with them. `Agreed`

#### Technical person for finishing the publishing on website ticket

* We need a volunteer with technical skills to finish the implementation of the release process so we can publish the list on the website. `ToDo`
