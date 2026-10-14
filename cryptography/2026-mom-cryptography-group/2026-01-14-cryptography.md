# SPDX Cryptography Meeting 2026-01-14

###### tags: `ToDo` `Question` `Agreed`

:::info
- **Where:** Remote through [Jitsi](https://meet.jit.si/SPDXCryptoMeeting)
- **When:** Every Wednesday at 14:00 UTC for 30 minutes
- References:
   - Past [MoMs](https://github.com/spdx/meetings/tree/main/cryptography)
   - Crypto algorithms [list](https://github.com/spdx/crypto-algorithms)

## Attendees

* [x] Bob Martin
* [x] Alfred Strauch
* [x] Steven Carbno
* [x] Agustín Benito Bethencourt
* [ ] Quique Goñiz


## Agenda

1. News
2. Certificates
3. References
4. Next steps

:::

## MoM

### News

* Monthly SPDX meeting tomorrow
* Agustin have pinged several quantum readiness experts from big corps so they know of our existenace. No feedback.
* X509 OID property removed. Call for review: [PR50](https://github.com/spdx/cryptographic-algorithm-list/pull/50) `ToDo`
* We are starting to use the existing labels on our issues and PRs

### Certificates

* Instead of developing the conversation about including the certificates or not on [#36](https://github.com/spdx/cryptographic-algorithm-list/issues/36) Agustin have created a specific issue for it [#49](https://github.com/spdx/cryptographic-algorithm-list/issues/49)
   * Use a specific "cryptoclass: protocol" is the main proposal

### References

* First Batch of references: call for review [PR48](https://github.com/spdx/cryptographic-algorithm-list/pull/48) `ToDo`
* Second batch of references: WIP [#9](https://github.com/spdx/cryptographic-algorithm-list/issues/9#issuecomment-3749348341) `ToDo`

### Next steps

These are the priorities including issues that describe all or part of the work to be tackled

1. Insist in adding oid and reference values in the algorithms descriptions: #9
2. Sart working on the parameter idea, starting with modes: #25, #39, #21
3. Solve the challenge of having different evolutions of the same algorithm: #44, #47, #49, #4
4. Reduce the friction for newcomers: #33 #41 #42
5. Add new algorithms to the list: #43
