# SPDX Cryptography Meeting 2026-02-11

###### tags: `ToDo` `Question` `Agreed`

:::info
- **Where:** Remote through [Jitsi](https://meet.jit.si/SPDXCryptoMeeting)
- **When:** Every Wednesday at 14:00 UTC for 30 minutes
- References:
   - Past [MoMs](https://github.com/spdx/meetings/tree/main/cryptography)
   - Crypto algorithms [list](https://github.com/spdx/crypto-algorithms)

## Attendees

* [x] Bob Martin
* [x] Alfred Strauch
* [x] Steven Carbno
* [x] Agustín Benito Bethencourt
* [ ] Quique Goñiz
* [x] Stefan-Lukas Gazdeg
* [x] Victor Lu
* [x] Jan Klaussner


## Agenda

1. News
2. Security Group coordination with the Cryptography Group
3. List publishing
4. Release policy

:::

## MoM

### News

* First timers at the meeting: introductions
* Tomorrow Thursday at 16:00 UTC Gary will go over the List Publisher. Link to the [invitation](https://meet.jit.si/SPDXCryptoMeeting)
    * Announced it on the spdx mailing list so others can join
* 2025q4 and 2026 MoM merged into the meetings folder. 2025q3 still in PR state. Probably overseen
    * Alexios requested a single PR per MoM from now on. We will do

### Security Group coordination with the Cryptography Group

* Alfred brings the need to coordinate in preparation for the tech-meeting next week
* Agustin will intro Steven during the presentation at the tech-meeting so Steven shows how the Security profile plans to make use of this List.
    * Steven shows what will be the core of his participation to the participants at the meeting

### List publishing

* Improved the ticket that tracks the publishing process [#51](https://github.com/spdx/cryptographic-algorithm-list/issues/51)
* Decision about the layout of the list has been [documented](https://github.com/spdx/cryptographic-algorithm-list/issues/51#issuecomment-3884964241)

### Release policy

* We have a [document](https://github.com/spdx/cryptographic-algorithm-list/issues/52#issuecomment-3884240415) that reflects what, formally, we should include in a release policy, which will be tracjed in [ticket #52](https://github.com/spdx/cryptographic-algorithm-list/issues/52). 
    * Now the idea is to focus on the minimum content that is required at this point.
        * Cadence: 
        * Versioning: 
        * Branching/Tagging policy: 

Check for reference
* the latest SPDX License List[release](https://github.com/spdx/license-list-XML/releases/tag/v3.27.0) 
* SPDX License List [release process](https://github.com/spdx/license-list-XML/blob/main/DOCS/release-process.md) for reference

#### Discussion

* Should we have a release cadence?
    * Is it a big burden to update the website? If no, we should not have a cadence
    * How long do we want to afford to have a mjissmatch between the website and the repo
    * Tomorrow we will find out if it is a big burden or not to publish on the website
    * We will refer users to the website or the automated output version
* We can have our own versioning
    * Versioning related to dates? yes, combine it with major release versioning 1.2026.03.15 mr.yyy.mm.dd.hh.mm mr=major release number 
* Branching/tagging: agreement on not having release branches. We will work on main
    * What will we do when we make a structural change? Can we push the complaexity of managing two different versions into the publisher instead of creating two release branches?

### AOB

* Should we start bringing here as first point of our agenda the approval of the previous minutes or is it too early?
    * We can mimic the Hardware procedure
    * Let's start now (next meeting)
* Discussion of the chacha / salsa case (algorithms evolution) to get early impressions from the participants.
    * No conclusions
