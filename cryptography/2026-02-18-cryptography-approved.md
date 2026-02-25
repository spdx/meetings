# SPDX Cryptography Meeting 2026-02-18

###### tags: `ToDo` `Question` `Agreed`

:::info
- **Where:** Remote through [Jitsi](https://meet.jit.si/SPDXCryptoMeeting)
- **When:** Every Wednesday at 14:00 UTC for 30 minutes
- References:
   - Past [MoMs](https://github.com/spdx/meetings/tree/main/cryptography)
   - Crypto algorithms [list](https://github.com/spdx/crypto-algorithms)
- Approved on: 2026-02-25

## Attendees

* [x] Bob Martin
* [x] Alfred Strauch
* [x] Steven Carbno
* [x] Agustín Benito Bethencourt
* [ ] Quique Goñiz
* [x] Jean Camp


## Agenda

1. News
2. Release policy
3. List diminutive

:::

## MoM

### News

* Quique might not have time to help us. He is currently overloaded, which is why we do not have yet the latest scanoss contribution
* Yesterday the SPDX CryptAlg was introduced to the tech group during the tech-meeting by Steven C. and Agustin B.B.
   * The slide deck was sent to the spdx-tech mailing list
   * Add ordinality to each property and define if the property is mandatory or not `ToDo`

### Release policy

* There is a draft for the first 3 sections of the release policy document. Check [Issue #52](https://github.com/spdx/cryptographic-algorithm-list/issues/52)
* Questions
   * Roles: do we adopt the concept of Release Manager?
       * We do not have a release manager but the Group will appoint a person to coordinate and execute the release tasks.
   * I suggest to create a list for downstream users so they get our announces and act accordingly. Specially relevant for hot releases.
       * Does SPDX has something similar to a spdx-announce list that we can use?
          * For announcements we will use the general spdx list and for alerts, focusing on downstream, we will create a specific list `Agreed`
* " Where circumstances require adjusting a release date or skipping a cycle, the decision will be documented and communicated through the usual channels."
    * Let's do the skipping a cycle a "no-action" event `Agreed`

### List diminutive

Can we adopt the following diminutives for the list?
* SPDX C.A.List
* SPDX CryptAlg `Agreed`
    * Add to the glossary section of the release policy and the readme `ToDo`
* CAList

### Properties

Conversation about the properties `ToDo`
1. Id: mandatory - unique `Agreed`
2. Oid: optional - unique but can be extended (check how oid works) We can use 0 to n . oid [0..*] `Agreed`
    * How is this done in YAML ?
3. Name: mandatory - unique `Agreed`
4. commonkeySize: optional - non unique `Agreed`
5. specifiedkeySize: optional - non unique `Agreed`
6. cryptoClass: mandatory - unique `Agreed`
7. cryptoSubClass: optional - unique `Agreed`
8. reference: mandatory - non unique `Agreed`

Future cases:
* Parameters should be optional
* alias: this could be an option for those cases where we need to refer to the id that cyclonedx uses or in case there is more than one id (pre / post standardization)

* Add a new bullet point per property description labeled "ordinality" `ToDo`

### Parameter: mode

Do we assume for now that mode is a parameter?
* It would make things easier for now
* Do we have a finite number of modes? So far, yes.
* Agreement to use mode as example on how users will use parameters vs properties
* MOde as a parameter for now `Agreed`
