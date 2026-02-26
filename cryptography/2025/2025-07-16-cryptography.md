# SPDX Cryptography Meeting 2025-07-16

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
[x] Victor Lu
[x] Pungav Sharma


## Agenda

1. News
2. Discussion / approval of the first draft of the list
3. AOB

:::

## MoM

### News

* The description of the properties has been improved in the kay range topic, according to the agreement held during the last meeting
   * Link to [properties](https://github.com/spdx/crypto-algorithms/issues/8#issuecomment-3025068280)
* Check the latest additions to the list
   * The TO and AND operators has been added to the key sizes attributes when appropiate
   * The SPDX license identifier is back to each .yaml file.
   * Link to [PR](https://github.com/spdx/crypto-algorithms/compare/main...toscalix:crypto-algorithms:main)

### Discussion / approval of the first draft of the list

Should we approve the current PR including the commit: c5ece8b26200a7f34e34742512aac217290b86f7 
* Check the link: https://github.com/spdx/crypto-algorithms/pull/12/commits 

There is a consensus on merging the PR to have a draft ready for OSS EU. `Agreed`
Call for review among the group. Ping Alexios for merging if no other within the meeting can. `ToDo`
   * Reviews takes place during the meeting.

### AOB

* OSS EU 2025 [talk](https://osseu2025.sched.com/event/25Vp2/know-your-crypto-standardizing-and-detecting-crypto-algorithms-the-open-source-way-matias-daloia-scanoss?iframe=no&w=100%&sidebar=yes&bg=no) where Matias, the speaker, can introduce at the end info about this list
* We analyse a document from cert-in.org.in where the regulator request certain information about algorithms for CBOMs for quamtum readiness.
    * Table 9 from the document http://www.cert-in.org.in/PDF/TechnicalGuidelines-on-SBOM,QBOM&CBOM,AIBOM_and_HBOM_ver2.0.pdf 
    * Should we add OID as property? `Question`
    * Add a new issue to discuss the addition of OID. This can be a [good reference](https://www.alvestrand.no/objectid/) `ToDo`
