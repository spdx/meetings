# SPDX Cryptography Meeting 2026-03-04

###### tags: `ToDo` `Question` `Agreed`

:::info
- **Where:** Remote through [Jitsi](https://meet.jit.si/SPDXCryptoMeeting)
- **When:** Every Wednesday at 15:00 UTC for 30 minutes
- References:
   - Past [MoMs](https://github.com/spdx/meetings/tree/main/cryptography)
   - SPDX Cryptogrphic Algorithms [list](https://github.com/spdx/cryptographic-algorithm-list)
- Approved: 2026-03-11

---

## Attendees

* [x] Bob Martin
* [x] Alfred Strauch
* [x] Steven Carbno
* [x] Agustín Benito Bethencourt
* [ ] Quique Goñiz


## Agenda

1. Approval MoM that took place on 2026-02-25
2. News
3. CryptAlg List deployment
4. Release policy

:::

## MoM

### Approval MoM that took place on 2026-02-25

* Please find the [MoM](https://hackmd.io/gg1oUSF6RP6hgjMowf6AoA)

* [x] Approved unanimously 

### News

* New PR to add cardinality to each of the properties: [PR 57](https://github.com/spdx/cryptographic-algorithm-list/pull/57/changes)
   * Reviewed by Stene and Bob. Some improvements suggested and applied. Merged

### List deployment

* The epic is described in the [issue #51](https://github.com/spdx/cryptographic-algorithm-list/issues/51)
   * Requirements discussion throughout the week.
      * Thanks Gary and Alexios for the support
      * We have an initial [draft of the requirements](https://github.com/user-attachments/files/25723251/spdx-crypt-alg-website-workflow.pdf)
   * The output repository has been created: [cryptographic-algorithm-list-data](https://github.com/spdx/cryptographic-algorithm-list-data)
      * Agustin and jeronimo have rights
      * Thanks Gary
   * The Issue corresponding to the documentation to be prepared for the initial release and deployment has been redefined: [Issue #56](https://github.com/spdx/cryptographic-algorithm-list/issues/56)
* We need to take a decision:
   * The current proposal is:
      * Working repository (input) name/URL: https://github.com/spdx/cryptographic-algorithm-list
      * Deployed list repository, including the list in .json format to target tooling, (output) name/URL: https://github.com/spdx/cryptographic-algorithm-list-data
      * Web page URL: https://spdx.github.io/cryptographic-algorithm-list
    * Alexios points out that there is a technical limitation that prevents us from having a URL different from the output repository name.
      * Can we overcome this technical challenge?
      * If we cannot, Agustin proposes:
         * Working repository (input) name: cryptographic-algorithm-list-devel
         * Deployed list repository (output) name: cryptographic-algorithm-list
         * Web page URL: cryptographic-algorithm-list

Discussion
* Do we ned the menu on the left?
   * If it is simpler to remove it, we do
   * If we do, make sure the version tag is added to the description box, just like the License List
* Do we need the navigation buttoms? 
   * Remove them if we can

* About the naming.... what if, instead of -devel we use -source ?
   * We will decide once we get the input from Jeronimo about option 1 (current proposal).

### Release Policy

Agustin keeps dedicating effort to the [Release policy](https://github.com/spdx/cryptographic-algorithm-list/issues/52).
* [Sections 8 and 9](https://github.com/spdx/cryptographic-algorithm-list/issues/52#issuecomment-3920996790) are new

Discussions
* CHANGELOG.md should be automatically generated. Developers submitting PRs should include the entry that will be added to the changelog. How? Let's investigate it.
   * Can we add a template to the PR where the submitter adds the content for the changelog?
