# SPDX Cryptography Meeting 2026-05-13

###### tags: `ToDo` `Question` `Agreed`

:::info
- **Where:** Remote through [Jitsi](https://meet.jit.si/SPDXCryptoMeeting)
- **When:** Every Wednesday at 14:00 UTC for 30 minutes
- References:
   - Past [MoMs](https://github.com/spdx/meetings/tree/main/cryptography)
   - SPDX Cryptogrphic Algorithms [list](https://github.com/spdx/cryptographic-algorithm-list)
- Approved: 2026-05-20

---

## Attendees

* [ ] Bob Martin
* [x] Alfred Strauch
* [x] Steven Carbno
* [x] Agustín Benito Bethencourt
* [x] Quique Goñiz


## Agenda

1. Approval MoM that took place on 2026-05-06
2. News
3. Presentation by SCANOSS showing how their product consumes SPDX CryptAlg
4. Parameters: mode
5. Property description file name adaptation
6. PQC classification proposal

:::

## MoM

### Approval MoM that took place on 2026-05-06

* Please find the [MoM](https://hackmd.io/wgZh5FzsQ_mrXk74kZp5Sg)

* [x] Approved unanimously 

### News

#### PRs and tickets

* Conflicts resolved and [PR#71](https://github.com/spdx/cryptographic-algorithm-list/pull/71) was merged. The first step of the restructuring based on Karsten Klein's proposal is done
* During the meeting, we add some changes and resolved conflicts on [PR#60](https://github.com/spdx/cryptographic-algorithm-list/pull/60)

### Presentation by SCANOSS showing how their product consumes SPDX CryptAlg

Presentation by Quique about how SCANOSS consumes the SPDX CryptAlg data on a public repo under their GitHub org, merge it there with keywords for detection and consume it internally in their knowledge base to serve their users detecting the crypto algorithms they have in their software composition and decorate the data they present to the user with the metadata from the List. The main use case is Export Control.

Quique talked about the coming improvememnts in the current toolchain/process to promote deduplication and to move the hub repo to Software Transparency Foundation so other SCA and security tooling developers can use it and contribute back to the repo, incase they contribute keywords or reg. explressions and directly upstream, like SPDX CrypAlg if they contribute metadata or new algorithms.

### Parameters: mode

Agustin is working on different proposals to discuss them within the Cryptography Group. You can find a WIP version of the proposal in the [Issue#39](https://github.com/spdx/cryptographic-algorithm-list/issues/39#issuecomment-4440988937)

### Property description file name adaptation

* A new sub-issue [Issue#76](https://github.com/spdx/cryptographic-algorithm-list/issues/76) of the [Issue#39](https://github.com/spdx/cryptographic-algorithm-list/issues/39) has been created to track the required change in the name of the properties description file, once we add the parameter/mode description
   * Agustin had a half way coocked proposal for this. I just took another step and here is a draft to evaluate [Property description file name adaptation](https://github.com/spdx/cryptographic-algorithm-list/issues/76#issuecomment-4441048465)

### PQC classification proposal

* Since Agustin had it half way coocked, Agustin decided to mature the PQC classification proposal so others can give it a thought. Check [Issue#73](https://github.com/spdx/cryptographic-algorithm-list/issues/73#issuecomment-4440489353)
   * We will discuss it in coming weeks