# SPDX Cryptography Meeting 2025-09-24

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
* [x] Jean Camp
* [ ] yyyy


## Agenda

1. News
2. State of the current version: recap
3. Next steps to v0.1
4. Parameter
5. Changing the name of the property proposal: origin (no time)
6. Pending requests (no time)
7. AOB

:::

## MoM

### News

* New PR to [remove the TO operator](https://github.com/spdx/crypto-algorithms/pull/26)
* Two new tickets (discussions): 
   * Add [parameter](https://github.com/spdx/crypto-algorithms/issues/25) as property to the list
   * Change the [repo name](https://github.com/spdx/crypto-algorithms/issues/27)
* New commit to the existing [list properties description PR](https://github.com/spdx/crypto-algorithms/commit/fb6a53f1ff7c262ce62f085ab9a070d32e5dd700)
   * With this new commit, all the comments from Alexios has been addressed.
   * Agustin requested new reviews so Alexios review it too
* [Issue 10](https://github.com/spdx/crypto-algorithms/issues/10) was closed

### State of the current version: recap

The following changes has been proposed and submitted as PR to the first version of the list
* Properties description file, including the descriptions to all the changes below. [PR15](https://github.com/spdx/crypto-algorithms/pull/15)
* New way to express several integer values in KeySize related properties. [PR23](https://github.com/spdx/crypto-algorithms/pull/23)
* New way to express ranges of integer values in keySize related properties[PR26](https://github.com/spdx/crypto-algorithms/pull/26)
* Fixes to different algorithms that lacked information or had it wrong [PR24](https://github.com/spdx/crypto-algorithms/pull/24)

### Next steps to v0.1

Have this PRs reviewed and merged so we can tag the list as v0.1

Additional improvements:
* Develop the README
   * Include the [group charter](https://github.com/spdx/crypto-algorithms/issues/13)
   * Agustin will make a proposal `ToDo`
   * * Suggestion to add CBOM as keyword in the readme `Agreed`
* Change the [repo name](https://github.com/spdx/crypto-algorithms/issues/27) to a more descriptive one
   * Agreement on calling it cryptographic-algorithms-list `Agreed`
* No tagging until we get to v1.0 

### SPDX Crypto Algorithms List v0.2 roadmap

* New properties
   * OID `Agreed`
   * [Origin](https://github.com/spdx/crypto-algorithms/issues/9) `Question`
* New algorithms
   * To be contributed by SCANOSS `ToDo`
* Concentrate all the [references and links](https://github.com/spdx/crypto-algorithms/issues/19) in one place
* New property request: parameter
* Template document added
   * Turn this into a ticket `ToDo`

### New property request: parameter

Steven suggested to add this property as requested by the Security profile
* [Link](https://github.com/spdx/crypto-algorithms/issues/25) to description
* parameter is described in the list properties description document but the values do not going the list itself but they are meant to be used in spdx documents
* create a PR about this `ToDo`

### Changing the name of the property proposal: origin 

Which name do we assign to this property?

Background of the [proposal/discussion](https://github.com/spdx/crypto-algorithms/issues/9)
* General consensus on adding it
* origin is not a good name

### Pending requests

* Persistent URIs for the RDF
   * What do we do with [this request](https://github.com/spdx/crypto-algorithms/issues/6)
* How to declare [CMVP certificate](https://github.com/spdx/crypto-algorithms/issues/4) in SPDX?
* Characteristic of a [hash/encrypted output](https://github.com/spdx/crypto-algorithms/issues/5)

### AOB

* Agustin will make some noise about the list so we can have more people joining
