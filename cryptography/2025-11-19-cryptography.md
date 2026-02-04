# SPDX Cryptography Meeting 2025-11-19

###### tags: `ToDo` `Question` `Agreed`

:::info
- **Where:** Remote through [Jitsi](https://meet.jit.si/SPDXCryptoMeeting)
- **When:** Every Wednesday at 15:00 UTC for 30 minutes
- References:
   - Past [MoMs](https://github.com/spdx/meetings/tree/main/cryptography)
   - Crypto algorithms [list](https://github.com/spdx/crypto-algorithms)

## Attendees

* [ ] Bob Martin
* [x] Alfred Strauch
* [x] Steven Carbno
* [x] Agustín Benito Bethencourt
* [ ] Quique Goñiz
* [x] Victor Lu


## Agenda

1. News
2. Reference as property
3. AOB

:::

## MoM

### News

* CycloneDX cryptographic algorithm definitions and schema references added to our [references ticket](https://github.com/spdx/cryptographic-algorithm-list/issues/19#issuecomment-3552925559)
* Conclusions and questions from last meeting about Mode as parameter added to the corresponding ticket [Issue#39](https://github.com/spdx/cryptographic-algorithm-list/issues/39#issuecomment-3552945552)

### Reference as property

Based on our conversations during the [previous meeting](https://github.com/spdx/meetings/pull/947/commits/6f6de7f75c418094a3ed88540a1c6f6d081c2bcb), here is a proposal for the reference property description: Comment on [ticket #9](https://github.com/spdx/cryptographic-algorithm-list/issues/9#issuecomment-3552868454)
* Steven: Should we consider cases where the reference is not an URL? A ISBN of a book can be an example. `Question`
* If nobody raise any concern of feedback, we will consider this property description as solid. `Agreed`

Agustin started the list of at least 20 references. Check the [issue#9](https://github.com/spdx/cryptographic-algorithm-list/issues/9#issuecomment-3553145225)
   * Agustin will add those already found by CycloneDX for the coming meeting. Those including OIDs should also lead to a reference easily
   * Many of the references provided by list or pages in internet or AI services do not work, has moved or are not accessible.
   * Add another column including a checkbox to assure a second person has checked the reference so we reduce the risk of mistakes at PR stage

### AOB



