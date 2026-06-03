# SPDX Cryptography Meeting 2025-07-09

###### tags: `ToDo` `Question` `Agreed`

:::info
- **Where:** Remote through [Jitsi](https://meet.jit.si/SPDXCryptoMeeting)
- **When:** Every Wednesday at 14:00 UTC for 30 minutes
- References:
   - Past [MoMs](https://github.com/spdx/meetings/tree/main/cryptography)
   - Crypto algorithms [list](https://github.com/spdx/crypto-algorithms)

## Attendees

[ ] Bob Martin
[ ] Alfred Strauch
[x] Steven Carbno
[x] Agustín Benito Bethencourt
[x] Quique Goñi
[x] Victor Lu


## Agenda

1. News
2. Review the list. Is it ready to be merged as the first draft of the list?
3. Attributes or properties description: CycloneDX description
4. Is it the current way to express ranges ok?
5. AOB
 

:::

## MoM

News
* HackMD for minutes taking
* Charter ticket [closed](https://github.com/spdx/crypto-algorithms/issues/13)
* Cyclone DX properties description added to ticket [#8](https://github.com/spdx/crypto-algorithms/issues/8#issuecomment-3051861762)
* commonkeySize and specifiedkeySize [descriptions modified](https://github.com/spdx/crypto-algorithms/issues/8#issuecomment-3025068280) as per last meeting agreement

Review the list. 
* Add the SPDX license ID `ToDo`

Is it the current way to express ranges ok?
* Quique makes a proposal on how to deal with limited number of key sizes vs a range, using the AND
* Instead of using the "-" to express ranges, we will use "TO" `Agreed` `ToDo`
* How do we want to represent infinite key size possibilities? `Question`
    * Can we simply not add anything
* How do we represent a minimum key size to infinity range? `Question`
    * It seems that representing a maximum is an easier case.

AOB
* We all agree we should talk to CycloneDX and try to agree on the identifiers (id) `Agreed`




