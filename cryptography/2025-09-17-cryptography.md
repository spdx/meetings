# SPDX Cryptography Meeting 2025-09-17

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
2. Range of values proposal
3. Conversation at the SPDX security group

:::

## MoM

### News

* Operators. Alexios suggests to use the default yaml way of expressing arrays of values and ranges.
   * I found the proposal simpler than us inventing a new way. This line of thinking can be applied also to the value ranges `Agreed`
   * New PR to remove the AND operator https://github.com/spdx/crypto-algorithms/pull/23
* Minor fixes [submitted](https://github.com/spdx/crypto-algorithms/pull/24) to some of the algorithms of the list 

### Range of values proposal

* Check [this proposal](https://github.com/spdx/crypto-algorithms/issues/16#issuecomment-3303033314), following the yaml syntax
   * If we have two ranges we can go, for instance: specifiedkeySize: [{min: '224', max: '512'},{min: '1024', max: '2048'}] `Question`

### Conversation at the SPDX security group

* Steven introduces the concept of "parameter" to address the explosion of options we should consider with keySize including modes of operations. aes is a good example. This came in a discussion during a security profile conversation
   * Steven will provide an example describing the proposal in a new issue  `ToDo`
