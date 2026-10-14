# SPDX Cryptography Meeting 2025-11-26

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
* [x] Victor Lu


## Agenda

1. News
2. Reference property
3. Pull Requests
4. AOB

:::

## MoM

### News

* Abstracts about our effort sent to the CfP of the following events:
   * [Code and Compliance](https://www.eclipse-foundation.events/event/code-compliance-2026/summary), organised by Eclipse ORC WG
   * [Security Devroom](https://github.com/security-devroom/fosdem-2026) at FOSDEM 2026

### Reference property

* A couple more references added to the [ticket #9](https://github.com/spdx/cryptographic-algorithm-list/issues/9#issuecomment-3553145225)

### Pull Request

Discussion: there is only handful of people who can merge PRs.
* Write to Alexios and Kate so more people other than Alexios can merge Pull Requests since only the owner can currently merge PRs `Agreed` `ToDo`

Dicussion about a policy for PRs
If we are adding a new property, the corresponding PR should provide
* the property description and values, affecting the crypto-algorithms-list-properties-description.md file
* The algorithm example, affecting the contributing.md
* The affected algorithms or, if they are too many, a first bulk of affected algorithms.
* The property entry in 5 algorithm yaml. files (suggestion).

Create a ticket with this policy to ground it and discuss it next week. `ToDo`

### AOB

Relation between a certificate from the security profile and this list. 
* The certificate, if it is an algorithm, should be included in the list with the corresponding ID, which will be used in the security profile. This is similar to a key. 
