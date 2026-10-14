# SPDX Cryptography Meeting 2026-04-22

###### tags: `ToDo` `Question` `Agreed`

:::info
- **Where:** Remote through [Jitsi](https://meet.jit.si/SPDXCryptoMeeting)
- **When:** Every Wednesday at 15:00 UTC for 30 minutes
- References:
   - Past [MoMs](https://github.com/spdx/meetings/tree/main/cryptography)
   - SPDX Cryptogrphic Algorithms [list](https://github.com/spdx/cryptographic-algorithm-list)
- Approved: 2026-04-29

---

## Attendees

* [x] Bob Martin
* [x] Alfred Strauch
* [x] Steven Carbno
* [x] Agustín Benito Bethencourt
* [ ] Quique Goñiz
* [x] Karsten Klein
* [x] Mahshid Izady


## Agenda

1. Approval MoM that took place on 2026-04-15
2. News
3. cryptoClass Structure

:::

## MoM

### Approval MoM that took place on 2026-04-15

* Please find the [MoM](https://hackmd.io/SMNUq7mmTyCX8P0o77UdJA)

* [x] Approved unanimously 

### News

* Conversation about how CBOM will be used in orgaizations.
   * We are in a phase trying to set the expectations for CBOMs and the relation with certificates and cryptography
   * For cryptography it might be export control and PQC the main drivers/scenarios
   * [Reference 1](https://atis.org/preparing-telecom-for-the-quantum-safe-future-why-a-telecom-specific-cbom-matters/) [Reference 2](https://eur02.safelinks.protection.outlook.com/?url=https%3A%2F%2Fgithub.com%2Fatisorg%2Fcyclonedx-property-taxonomy&data=05%7C02%7Cmahshid.izady-vahedy%40ericsson.com%7C6c403d6c2d084cd9e12708dea06bfc50%7C92e84cebfbfd47abbe52080c6b87953f%7C0%7C0%7C639124582869389501%7CUnknown%7CTWFpbGZsb3d8eyJFbXB0eU1hcGkiOnRydWUsIlYiOiIwLjAuMDAwMCIsIlAiOiJXaW4zMiIsIkFOIjoiTWFpbCIsIldUIjoyfQ%3D%3D%7C0%7C%7C%7C&sdata=Q%2FyZ9HRVnnqbiukmXUpN9KHIDuQnBGWgUBSENLA%2FqAM%3D&reserved=0)
* Request from Bob: Add the request here `ToDo`. We will track it in coming meetings

### cryptoClass Structure 

Agustín has analysed how would our current list fit into the new cryptoClass structure proposed. Please check the result and some notes [Issue #68](https://github.com/spdx/cryptographic-algorithm-list/issues/68)

Karsten has done some work on Composite algorithms which supports the current discovery. He showed that effort

Tests: `ToDo`
* panama does not challenge the structure for now. Pick up one and we can add a comment
* PQC is not a cryptoClass but a property
   * Description
   * Cardinality [0..1]
   * Values: "has-based", "code-based" or "lattice-based"
* Composite
    * Let's focus on this after we solve the PQC.

Agustin will add these decisions on the current List structure so we can review it. `ToDo`
