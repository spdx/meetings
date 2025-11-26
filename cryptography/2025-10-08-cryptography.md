# SPDX Cryptography Meeting 2025-10-08

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
* [x] Quique Goñiz


## Agenda

1. News
2. Discussion about the property "parameter"
3. OID property description and values. Review amd discussion
4. CONTRIBUTING.md file
5. AOB

:::

## MoM

### News

* 4 PRs merged:
    * New algorithms definitions: part 1[#28](https://github.com/spdx/cryptographic-algorithm-list/pull/28/commits/e1884735bbe59f0286b968b4dd5e1de572fc2ea8)
    * Quique introduce the new algorithms
    * Discussion about cbc which seems a mode of operation
    * yaml compatible expression instead of operator TO [#26](https://github.com/spdx/cryptographic-algorithm-list/pull/26)
    * Minor fixes and additions on some of the algorithms of the list [#24](https://github.com/spdx/cryptographic-algorithm-list/pull/24)
    * Crypto Algorithms List Properties Description [#15](Crypto Algorithms List Properties Description)
    
* One additional conflict resolved. Ready for review and merge[#23](https://github.com/spdx/cryptographic-algorithm-list/pull/23)

* Proposal for the [OID definition and values](https://github.com/spdx/crypto-algorithms/issues/20#issuecomment-3364940278)

* New PR. Update README.md [#29](https://github.com/spdx/cryptographic-algorithm-list/pull/29)
   * Given that the group charter is not something other groups are doing, Agustin added a section on the readme about the group.

* Agustin is creating a blog post for his blog about the list. Agustin would appreciate if somebody review it, in case there are mistakes. It will have the following structure
   * Background from agustin POV
   * Current status
   * Next steps: see [SPDX Cryptography Meeting 2025-09-24](https://github.com/spdx/meetings/pull/925/commits/655f8a504cb2bb2a223b75ba9e884c47197fbf68)
   * Call for participation
   * Personal experience so far


### Discussion about the property "parameter"

* Agustin was looking for the possible entries for the parameter property, in order to find out if the parameter concept is finite or it has so many options that we cannot tacle it. 
    * Agustin check the configuration parameters, defined them and check for their possible values.
    * The result of this effort is [in the ticket](https://github.com/spdx/crypto-algorithms/issues/25) 

Discussion
* Once we decide on how to approach this, we take a decision on removing or not the cbc algorithm `ToDo`
* Some parameters might be complex and might end up in its own folder `Question`

### OID property description and values. Review amd discussion

* Please check the [OID property description](https://github.com/spdx/crypto-algorithms/issues/20#issuecomment-3364940278)
* Discussion
* Do we turn it into a PR? `Question`
   * Unless we get comments on the ticket, we will turn this into a PR including:
       * The description we currently have on the ticket
       * A couple of OIDs added to a couple of algorithms so we at least have some examples. The rest will be added as we go


### CONTRIBUTING.md

Should we add a CONTRIBUTING.md file including: `Question`
* Instructions for requests
* Instructions for new algorithms
* Instructions for bugs
* Meetings information, so people join

If we agree on creating this, should we prioritise the template or this? `Question`

Discussion

* Let's add a contributing.md `Agreed` `ToDo` 
    * We will use the license list as template

### AOB

* Agustin will develop the issue "Create a cryptographic algorithm as example including every property" [#30](https://github.com/spdx/cryptographic-algorithm-list/issues/30)
* Alfred asks if this is just a list or a profile `Question`
    * Should it be related with the Security Profile?
        * The list could be added as appendix so it will require a proper description
    * How does SPDX describes the License List?
        * Check the [license intro text](https://spdx.org/licenses/) as template 
        * Agustin will create a draft based on the SPDX License List description `ToDo`
