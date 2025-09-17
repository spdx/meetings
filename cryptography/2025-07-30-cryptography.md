# SPDX Cryptography Meeting 2025-07-30

###### tags: `ToDo` `Question` `Agreed`

:::info
- **Where:** Remote through [Jitsi](https://meet.jit.si/SPDXCryptoMeeting)
- **When:** Every Wednesday at 14:00 UTC for 30 minutes
- References:
   - Past [MoMs](https://github.com/spdx/meetings/tree/main/cryptography)
   - Crypto algorithms [list](https://github.com/spdx/crypto-algorithms)

## Attendees

[x] Bob Martin
[x] Alfred Strauch
[x] Steven Carbno
[x] Agustín Benito Bethencourt
[x] Quique Goñiz
[ ] Victor Lu


## Agenda

1. News
2. AOB

:::

## MoM

### News

* Comments from Alexios on the group charter.
   * It seems there are no other group who needed a charter. I justified our need.
   * Group vs Team. Alexios explained the vocabulary used at SPDX
   * Mission and strategic goal sounds like we are challenging the ones for the whole SPDX. Erased them. The core text is the goal.
   * With this, as soon as the PR for the list is approved, I will submit this one. `ToDo`
* Agustin pinged Kate and Gary, with Alexios in CC, to have the PR merged.

### AOB

* Approach to detect Signatures Algorithms in source code: Quique
    * Regex expressions analysing in order to catch keywords. We might want to detect which kind of signature algorithm it is.
    * We should go through a big list of libraries that define signatures. Maybe we can define a subset of librearies so we can get a set of keywords we can then generalise.
    * Sempgrep could be a tool we can also use.
    * Quique claims that it will not be an easy task which is why we should start with a subset of libraries we know that implement signature algorithms.
        * This use case is trickier than others that led to the current list.
    * Quique has a couple of lists in mind. Others can contribute through a ticket. `Agreed` 
* Crypto talks at OSS EU
    * [Cryptography Support in Zephyr: Recent Changes and Upcomings - Valerio Setti, BayLibre](https://osseu2025.sched.com/event/25Vm2/cryptography-support-in-zephyr-recent-changes-and-upcomings-valerio-setti-baylibre?iframe=no&w=100%&sidebar=yes&bg=no)
    * [Know Your Crypto: Standardizing and Detecting Crypto Algorithms the Open Source Way - Matias Daloia, SCANOSS](https://osseu2025.sched.com/event/25Vp2/know-your-crypto-standardizing-and-detecting-crypto-algorithms-the-open-source-way-matias-daloia-scanoss?iframe=no&w=100%&sidebar=yes&bg=no)
* Where should we announce this group exist within SPDX?
    * There are several profiles: security, operations, AI, Functional Safety and software service. Agustin will join their mailing lists so he can join a meeting. `Todo`
        * Operations and services: ask Gary. Request a short call with him. `Todo`
        * Security: TBD
        * AI: TBD
        * Functional safety: TBD


