# SPDX Cryptography Meeting 2025-11-05

###### tags: `ToDo` `Question` `Agreed`

:::info
- **Where:** Remote through [Jitsi](https://meet.jit.si/SPDXCryptoMeeting)
- **When:** Every Wednesday at 10:00 UTC-4 for 30 minutes
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



## Agenda

1. News
2. OID pull request
3. Origin property: new name
4. Handling License Info
5. AOB

:::

## MoM

### News

* New [PR#37](https://github.com/spdx/cryptographic-algorithm-list/pull/37) about CONTRIBUTING.md
* New [PR#38](https://github.com/spdx/cryptographic-algorithm-list/pull/38) that closes two bugs
    * [Remove rsa-oaep since it is a specific configuration of rsa](https://github.com/spdx/cryptographic-algorithm-list/issues/34)
    * [Modes will not be considered algorithms. Remove Block Cipher Modes](https://github.com/spdx/cryptographic-algorithm-list/issues/32)
* [Issue #9](https://github.com/spdx/cryptographic-algorithm-list/issues/9) ready to work on

### OID pull request

* Agustin created a PR. 
* Steven reviewed it. There are several mistakes.
* Review of the OID[PR#35](https://github.com/spdx/cryptographic-algorithm-list/pull/35) by Steven
    * Agustin went over the review
    * Agustin added a [few links](https://github.com/spdx/cryptographic-algorithm-list/issues/20#issuecomment-3461707188) where you can check for OIDs

We went over the comments on the PR. Resolved.

Ticket [#36](https://github.com/spdx/cryptographic-algorithm-list/issues/36)
* what do we do with rijndael: Steve thinks that we can have two different algorithms with the same OID in cases like this one, where for NIST, both algorithms are the same with different parameters or one is the precursor of the other.
* X509 `ToDo`

### Origin Property: new name

Based on the discussion in issue [#9](https://github.com/spdx/cryptographic-algorithm-list/issues/9), here are suggestions for the property name.

* **reference**
   - **Pros**: Clear and neutral. Works for both original papers and standardization documents.
   - **Cons**: Generic term.
   - **Rationale**: Better than "origin" because it works for algorithms that went through revisions or standardization.
   - Opinions: preferred
* **algorithmReference**
   - **Pros**: Very explicit and unambiguous.
   - **Cons**: Longest option. Somewhat redundant since all properties are about algorithms.
   - **Rationale**: Leaves no doubt about what the property describes.
   - Opinions: redundant
* **specificationURL**
   - **Pros**: Very explicit. Follows the pattern of existing properties like `specifiedkeySize`.
   - **Cons**: Long name. The word "specification" might not fit all cases.
   - **Rationale**: Clear about what the link points to.
* **primaryReference**
   - **Pros**: Indicates this is the main source. Handles multiple revisions well.
   - **Cons**: Longer name.
   - **Rationale**: "Primary" solves the revision problem mentioned in issue #9.
   - Opinions: we would have to structure (arbitrate) priorities. Not a good one right now
* **publicationLink**
   - **Pros**: Clear about linking to published work.
   - **Cons**: Not all algorithms have formal publications.
   - **Rationale**: Works well for academic papers.
* source
* specification
* referenceStandard

Any other suggestion?

Which one should we go for?

* Steven and Agustin would go for **reference**
    * Since there is not enough participation to consider this an agreement, we will confirm it during the next meeting. `ToDo`
    * In the meantime, we will go with reference as property name
* Agustin will now move into describing the property `ToDo`

### Handling algorithms Info

Agustin: While checking the description of the SPDX License List, I realised we haven´t described how to use the identifier.

Check the SPDX License [Handling License Info](https://spdx.dev/learn/handling-license-info/) page

* Is this something we should do in the context of this list? `Question`
    * If yes, any thought about it that Agustin should consider in order to do a draft?
        * Agustin will create an issue
    * If no, who should do it, so we add such request? 

We think this is something we should do. `Agreed`

## AOB

Victor Lu: conversation to clarify what we are doing here with this list vs what CycloneDX is doing: differences and similarities
