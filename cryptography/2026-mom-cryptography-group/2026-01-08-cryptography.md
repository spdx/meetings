# SPDX Cryptography Meeting 2026-01-07

###### tags: `ToDo` `Question` `Agreed`

:::info
- **Where:** Remote through [Jitsi](https://meet.jit.si/SPDXCryptoMeeting)
- **When:** Every Wednesday at 14:00 UTC for 30 minutes
- References:
   - Past [MoMs](https://github.com/spdx/meetings/tree/main/cryptography)
   - Crypto algorithms [list](https://github.com/spdx/crypto-algorithms)

## Attendees

* [x] Bob Martin
* [ ] Alfred Strauch
* [x] Steven Carbno
* [x] Agustín Benito Bethencourt
* [ ] Quique Goñiz
* [x] Dave 
* [x] Teddy Nyambe


## Agenda

1. News
2. Does X509 belong to the List? 

:::

## MoM

### News

* Dave and Teddy intro themselves.
* Both abstract sent to FOSDEM week events have been rejected
* Do we [add a cardinal](https://github.com/spdx/cryptographic-algorithm-list/pull/48#issuecomment-3703692202) to the reference attribute when there is more than one? `Question`

    * We are all in favour of making it as simple as possible for tooling so Quique's suggestion seems the best one. `Agreed` 
    * Agustin will implement this solution `ToDo`  

### Does X509 belong to the List?

Working on [issue #36](https://github.com/spdx/cryptographic-algorithm-list/issues/36) agustin arrived to the conclusion that it is questionable that X509 belongs to the list. Finding are summarised on the ticket. 

CycloneDX does not include it in their [registry](https://cyclonedx.org/schema/cryptography-defs.json)

* Discussion about how to consider cases like X509 The concept of primitive or compound arises.
* We have "protocol" as subclass already. Is this the right categorization for X509
* No croncrete idea on how to proceed so we will discuss this topic again in the near future
