# SPDX Cryptography Meeting 2025-11-12

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
* [x] Roberto Hueso Gómez
* [x] Agustin Isasmendi
* [x] Basil


## Agenda

1. News
2. Parameter 1: Mode
3. Property: reference

:::

## MoM

### News

* First summary of this Group in the SPDX monthly meeting

### Parameter 1: Mode

* New ticket related with Parameter: Mode [issue #39](https://github.com/spdx/cryptographic-algorithm-list/issues/39) including a first attempt to classify modes and provide the most relevant ones.
* Can we relate algorithms with modes? `Question`
    * If yes, we couls define provide on each algorithm description the acceptable mode or/and in the mode description, which algorithms they are applicable to.
* CMAC, is it an algorithm or is it a mode?  `Question` `ToDo`
    * CycloneDX defines CMAC as an own algorithm. Since it's a MAC, not a cipher. 
* Check as reference: CycloneDX addresses a very similar task if definitng algorithms, including modes. It might make sense to sync that, see, for example: 
    * https://github.com/CycloneDX/specification/blob/3088143d8fcdc15e5ec635d1163685f2ef89678d/schema/cryptography-defs.json#L324
    * https://github.com/CycloneDX/specification/blob/3088143d8fcdc15e5ec635d1163685f2ef89678d/schema/cryptography-defs.schema.json

### Property: reference

First attempt to describe the property and questions related with the values. [issu #9](https://github.com/spdx/cryptographic-algorithm-list/issues/9#issuecomment-3522371746)

Do we allow more than one reference? `Question`
* If we do, we will do it like in other properties (YAML format)
* Assuming that several reference are possible, provide guidance on prioritization
* Official specification document (NIST, ISO, IETF, etc.) might be the one to propose as most relevant. Research might go second
    * All other option might be take as "guidance"
