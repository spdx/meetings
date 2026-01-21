# SPDX Cryptography Meeting 2025-0813

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
[ ] Quique Goñiz


## Agenda

1. News
2. List properties. Go over Alexios review
3. AOB

:::

## MoM

### News

* SPDX Groups presentations
   * At SPDX AI group meeting
   * At the SPDX August General Meeting
* Any feedback? 
   * The security and operations group are expected to be the first ones to reference this. 

### List properties. Go over Alexios review

Link to [the PR](https://github.com/spdx/crypto-algorithms/pull/15)

* Agustin addressed 4 of the 6 comments.
   * Check [commit](https://github.com/spdx/crypto-algorithms/pull/15/commits/710ddbe9c962606626c8a57c2c5ed6cd37acfb48)
   * Check [commit](https://github.com/spdx/crypto-algorithms/pull/15/commits/3d67d8062806facb5827e914351b773061b61e64)
* 2 comments need review:
   * Comment [1](https://github.com/spdx/crypto-algorithms/pull/15#discussion_r2259255438)
      * We do not expect the list to be part of a model unless a profile take elements of the list
      * Open a ticket with this task for September, since it affect the list `ToDo` 
   * Comment [2](https://github.com/spdx/crypto-algorithms/pull/15#discussion_r2259270084) 
      * We will answer in a similar way than before. In this case we wll add the values in the porpoerties ToDo`
      * Is cryptoSubClass the way to go?
         * There might be combinations of subclasses. We might ned to go for a template
         * [cryptoClass]/[cryptoSubClass]/[cryptoSubSubClass] 

### AOB

* CycloneDX references
   * Add these links to the corresponding ticket[1](https://github.com/CycloneDX/specification/blob/1.7-dev-cryptography/schema/cryptography-defs.json)[2](https://github.com/CycloneDX/specification/blob/1.7-dev-cryptography/schema/cryptography-defs.schema.json) `ToDo`
   * Do we include the properties of the algorithms in the future? Steven describes ideas on a way to move forward
* Curve as class? Defines a specific elliptic curve and its metadata. `Question`
