# SPDX Cryptography Meeting 2025-12-05

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
* [x] Victor Lu
* [x] Jean Camp


## Agenda

1. News
2. References
3. Rounds. New potential parameter?

:::

## MoM

### News

* GitHub IDs from Bob, Steven and Agustin sent to Alexios so they get merge permissions
* New [PR #45](https://github.com/spdx/cryptographic-algorithm-list/pull/45) that fixes Issue [#40](https://github.com/spdx/cryptographic-algorithm-list/issues/40)
* Any meeting out of devrooms at FOSDEM
* Call for Papers: Workshop on Security and Privacy in Standardized IoT (SDIoTSec) 2026. Send abstract about the list to Jean so she can submit it.
   * Agustin will provide the same abstract sent to the fosdem security devroom `ToDo`
* For FOSDEM, we want to have the reference property merged and the example of the process to propose a new algorithm.
   * Can we get there with the parameter discussion (mode or round) matured so we can provide a skeleton/showcase? `Question`
* Meetings on Dec 24th and Dec 31st get cancelled. Agustin will not attend to the next meeting 
* Victor provides a [reference](https://pkic.org/events/2025/pqc-conference-austin-us/THU_PLENARY_1230_Alexander-Lo%CC%88w_Practical-Insights-from-Following-NIST-SP-1800-38B.pdf)

### References

* Additional work on the references [list](https://github.com/spdx/cryptographic-algorithm-list/issues/9#issuecomment-3553145225)
   * The [first batch](https://github.com/spdx/cryptographic-algorithm-list/issues/9#issuecomment-3636883868) of references is ready.
   * Next step: create a PR including:
      * Property [description and values](https://github.com/spdx/cryptographic-algorithm-list/issues/9#issuecomment-3552868454)
      * Entry to the example algorithm

### Rounds. New potential parameter?

New issue to evaluate how to treat the specific case of Salsa and Chacha which, depending on the number of rounds, they can be named as, for instance, chacha8, chacha12 or chacha20 [#44](https://github.com/spdx/cryptographic-algorithm-list/issues/44)
* New PR to change the chacha(salsa) id [PR#46](https://github.com/spdx/cryptographic-algorithm-list/pull/46)
