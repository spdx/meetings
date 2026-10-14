# SPDX Cryptography Meeting 2026-05-20

###### tags: `ToDo` `Question` `Agreed`

:::info
- **Where:** Remote through [Jitsi](https://meet.jit.si/SPDXCryptoMeeting)
- **When:** Every Wednesday at 15:00 UTC for 30 minutes
- References:
   - Past [MoMs](https://github.com/spdx/meetings/tree/main/cryptography)
   - SPDX Cryptogrphic Algorithms [list](https://github.com/spdx/cryptographic-algorithm-list)
- Approved: 2026-05-27

---

## Attendees

* [ ] Bob Martin
* [x] Alfred Strauch
* [x] Steven Carbno
* [x] Agustín Benito Bethencourt
* [ ] Quique Goñiz
* [x] Karsten Klein


## Agenda

1. Approval MoM that took place on 2026-05-13
2. News
3. cryptoSubClass values
4. Parameters

:::

## MoM

### Approval MoM that took place on 2026-05-13

* Please find the [MoM](https://hackmd.io/EvDaA1vLQ4eIQKu5HUP43w)

* [x] Approved unanimously 

### News

#### Issues and PRs updates

* Reorganising the meetings folder before sending more MoMs for approval
   * Restructuring [PR#1109](https://github.com/spdx/meetings/pull/1109)
   * Closed unapproved PRs. Once the restructuring is approved I will resend these in a bulk
   * The latest MoMs will be submitted in a one by one basis, as requested by Alexios
* [Issue#69](https://github.com/spdx/cryptographic-algorithm-list/issues/69) is closed after merging the List restructuring
* Correction of cmac
    * I introduced cmac in the last minute in a PR to correct a mistake from my side, but I did it with the former list structure, not the new one. [PR#77](https://github.com/spdx/cryptographic-algorithm-list/pull/77) adds to cmac the right cryptoClass value

### cryptoSubClass values

The cryptoSubClass corresponding to the newly created cryptoClass have no values. [Issue#72](https://github.com/spdx/cryptographic-algorithm-list/issues/72) tracks the discussion about those values
* Agustin has flashed a [quick proposal](https://github.com/spdx/cryptographic-algorithm-list/issues/72#issuecomment-4498965822) for evaluation.
* You can also find the [algorithms affected](https://github.com/spdx/cryptographic-algorithm-list/issues/72#issuecomment-4498966911)

### Parameters

Agustin suggest to give to the proposal a thought so he can mature a proposal. Which way do w go?

There is consensus on going for the proposal 2 style, considering Steven's [PR#67](https://github.com/spdx/cryptographic-algorithm-list/pull/67/changes)
* [Resource as guidance](https://strictdoc.readthedocs.io/en/stable/stable/docs/strictdoc_01_user_guide.html#SECTION-UG-DOCUMENT-GRAMMAR)

Agustin will try to flash a proposal based on a mix of proposal 2 and Steven's PR `ToDo`
