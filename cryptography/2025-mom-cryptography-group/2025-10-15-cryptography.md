# SPDX Cryptography Meeting 2025-10-15

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
* [x] Raymond Sheh
* [x] Emily Fox


## Agenda

1. News
2. OID
3. AOB

:::

## MoM

### News

* Agustin published a blog post about this effort: [Introducing the SPDX Cryptographic Algorithm List: a Personal View](https://toscalix.com/2025/10/14/introducing-the-spdx-cryptographic-algorithm-list-a-personal-view/)
    * 80 views so far
    * Promoted through social media
* [List](https://github.com/spdx/cryptographic-algorithm-list/issues/20#issuecomment-3406360631) of algorithms from the list that have OIDs
* Ticket [#13](https://github.com/spdx/cryptographic-algorithm-list/issues/13) closed. The text from the group charter is in the readme.md file
* Add CONTRIBUTING.md to the repo ticket [#31](https://github.com/spdx/cryptographic-algorithm-list/issues/31)
* Bug. Modes will not be considered algorithms. Remove Block Cipher Modes [#32](https://github.com/spdx/cryptographic-algorithm-list/issues/32) `ToDo`
* Intro text for the List. Request created but WIP [#33](https://github.com/spdx/cryptographic-algorithm-list/issues/33) `ToDo`
* In the security meeting there was a conversation about the algorithms modes. They want them reflected on the list.
    * What about in a subdirectory? `Question`
    * Add this proposal to the parameters and bug about mode tickets `ToDo`

### OID

* We have an initial [List](https://github.com/spdx/cryptographic-algorithm-list/issues/20#issuecomment-3406360631) of algorithms with OID. We need to
   * Confirm them
   * Add them to the list

Where do we add them? `Question` Options:
1. Right below the SPDX ID, since this is an identifier
2. Right below the Name, since ID and Name are the essential parameters
3. Below the parameters that provide structure to the algorithms, because these are the following in relevance
4. Below the keysize parameters (at the end) because keysizes are more relevant thatn the OID

There is a consensus that 1. is the right option `Agreed`

### AOB

* Short discussion about the organizations associated to the OID. 
    * Given that this is related with the origin discussion, since both include links, we will keep talking about this topic
