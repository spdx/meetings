# SPDX Cryptography Meeting 2025-10-22

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
* [x] Jean Camp


## Agenda

1. News
2. CONTRIBUTING.md
3. properties
4. AOB

:::

## MoM

### News

* [OID PR](https://github.com/spdx/cryptographic-algorithm-list/pull/35) has been created. 33 algorithms included OID
* New [Bug](https://github.com/spdx/cryptographic-algorithm-list/issues/34)
* The [task description #30](https://github.com/spdx/cryptographic-algorithm-list/issues/30) for the algorithm example is done

### CONTRIBUTING.md

This is [the link](https://github.com/spdx/cryptographic-algorithm-list/issues/31#issuecomment-3432168491) to the proposal made by Agustin
   * The first part of the text is inspired in the [CONTRIBUTING.md version](https://github.com/spdx/license-list-data/blob/main/CONTRIBUTING.md) of the SPDX License List 
   * The second part includes the example we agreed on creating. [#30](https://github.com/spdx/cryptographic-algorithm-list/issues/30)

* Steven: in the future we want to have the example as a template for tooling to validate the list. For now, it could be a good ideas as it is proposed
* Prepare the PR `ToDo`

### properties

Agustin: since we will not have algorithms, we might simply create a crypto-algorithms-list-configuration-description.md file and we add there, just like the properties, the description and potential values of the different configuration options, [similar to this](https://github.com/spdx/cryptographic-algorithm-list/issues/25#issuecomment-3365158539)

* We might have some cases where this approach might not work.
* Let's try to work an example for aes so we take decisions base on keeping the algorthms on the list simple enough to understand it, among other criteria.

### AOB
