# SPDX Cryptography Meeting 2026-07-08

###### tags: `ToDo` `Question` `Agreed`

:::info
- **Where:** Remote through [Jitsi](https://meet.jit.si/SPDXCryptoMeeting)
- **When:** Every Wednesday at 15:00 UTC for 30 minutes
- References:
   - Past [MoMs](https://github.com/spdx/meetings/tree/main/cryptography)
   - SPDX Cryptogrphic Algorithms [list](https://github.com/spdx/cryptographic-algorithm-list)
- Approved: 2026-07-15

---

## Attendees

* [ ] Bob Martin
* [x] Alfred Strauch
* [x] Steven Carbno
* [x] Agustín Benito Bethencourt
* [ ] Quique Goñiz
* [x] Karsten Klein


## Agenda

1. Approval MoM that took place on 2026-07-01
2. Meeting with the SPDX tech-team: retrospective
3. New on Agustin's involvement
4. Parameters proposal

:::

## MoM

### Approval MoM that took place on 2026-07-01

* Please find the [MoM](https://hackmd.io/cP3d2o3rR2Sy-OdLAvkK3w)

* [x] Approved unanimously 

### Meeting with the SPDX tech-team: retrospective

* Agustin did not attend. He sent the slides afterwards
    * Send the presentation to the tech-team mailing list `ToDo`
* Decisions on the meeting
    * List should be operational first. Prioritise going simple with parameters.
    * Kate will help bringing cryptographers.
    * We need a comprenhensive model the industry will accept
    * Syntax/grammar for identifiers. Use the license one as inspiration
        * Add a task for this including the references to the license list `ToDo`
    * Communicate with the lawyers involved in the license list. We can learn from them
    * We need to design the work required to push the list forward and find sponsorship to fund that work
        * Define a milestone we want to achive, the current status the team and skills we have and the gap we face to achieve that goal. That is what we need funding for.
            * It is unlikely that a single cryptographer can cover al the cases. 
        * Agustin will create a proposal on how to move forward on this. `ToDo`  

### New on Agustin's involvement

* STF sponsored me to work on the Cryptography Group tasks and meetings
    * The initial commitment was around 3 to 4 hours a week during six month, extended to a year.
    * I agreed with the STF Governing Board to extend it a third semester, reducing a bit the overall effort (2 to 3 hours per week). I was confident I could extended until the end of the year 2026.
* Sadly my consulting contract with STF has ended earlier than expected.
    * Next week will be the last one where I am involved with STF on regular basis, before my offboarding starts. So it will be my last week sponsored by STF to work here.
* Agustin will remain involved on best-effort basis.
    * The curernt involvement estimation is around 50% of today's effort, hopefully until the end of the year. That is around 1 to 2 hours per week, most of the weeks.
* Under the current circumstances, I suggest
    * My involvement move to a bi-weekly cadence.
        * Most of the relevant work I have been doing requires more than 1 to 2 hours of my time, to add meaningful value.
        * This measure would also reduce the amount of time I am involved in meetings
    * I am open to pass the coordination role to somebody else, who can be involved on weekly basis, if we want to keep the current cadence. 
    * I stop representing the Group in the monthly meetings, insisting on meeting time reduction
    * I keep doing the quarterly reports until somebody else pick up the task.
* My ultimate goal is to arrive to the end of 2026 have made an impact on the following topics:
   * The task related to subCryptoClass sorted
   * operationMode and keyLength parameters added
   * PQ algorithms taxonomy merged
   * Main PQ algorithms added to the list
   * MoMs merged
   * Cryptography Group continuity guaranteed 
   * Quarterly reports published.
       * Maybe an article summarising the overall activity in the SPDX web?

### Parameters proposal

* Some revision done
    * Checked some of the links to standrdization documents manually. 
    * Added or corrected 2 of the non-standard references: PCBC and IGE
    * Typos fixed: 3
* Create a PR excluding the extended form (qualifiers) in the description file and do not describe any algorithm using the extended form `ToDo`
    * Agustin will create a ticket including the description file additions and example (AES) required to support the extended form, for the record. `ToDo`