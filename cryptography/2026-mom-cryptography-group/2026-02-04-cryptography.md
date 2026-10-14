# SPDX Cryptography Meeting 2026-02-04

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


## Agenda

1. News
2. Website
3. AOB

:::

## MoM

### News

* FOSDEM week
    * FOSDEM [Fringe event](https://workshop.aboutcode.org/): conversation with OSPO crew from Nokia and with tooling developers about the List at the after event gathering
    * In general, people does not know we exist

### Website

* Agustin added the text that was created at the previous meetings to the [corresponding ticket #33](https://github.com/spdx/cryptographic-algorithm-list/issues/33#issuecomment-3846974600)
* Created an issue to collect the main actions required to publish the list on the website [issue#51](https://github.com/spdx/cryptographic-algorithm-list/issues/51)
* Ask Gary if he can help us understanding what it would require to make a sense of the publishing on the website and creating outputs in other formats process.  `ToDo` 
* We will put the parameters of the algorithms on each algorithm affected if that is the best way for the tooling to manage the information. KeySize is an example. `Agreed`
* Checking the [fields-xml.md](https://github.com/spdx/license-list-XML/blob/main/DOCS/xml-fields.md) file it might be that we first generate it and then we describe the xml fields in the document, instead of the other way around.
* Having 3 columns on the table is the way to go: full name, id and cryptoClass `Agreed`
* Create a PR/issue with the parameters we know about, so we can include them in the list. `ToDo`

### AOB

* These are the pending PRs including our MoMs
    * [PR947](https://github.com/spdx/meetings/pull/947)
    * [PR925](https://github.com/spdx/meetings/pull/925)
