# SPDX Cryptography Meeting 2025-07-23

###### tags: `ToDo` `Question` `Agreed`

:::info
- **Where:** Remote through [Jitsi](https://meet.jit.si/SPDXCryptoMeeting)
- **When:** Every Wednesday at 14:00 UTC for 30 minutes
- References:
   - Past [MoMs](https://github.com/spdx/meetings/tree/main/cryptography)
   - Crypto algorithms [list](https://github.com/spdx/crypto-algorithms)

## Attendees

[ ] Bob Martin
[x] Alfred Strauch
[x] Steven Carbno
[x] Agustín Benito Bethencourt
[x] Quique Goñiz
[ ] Victor Lu


## Agenda

1. News
2. Next steps
3. Is a digital signature algorithm a crypto algorithms?

:::

## MoM

### News

* Mail sent to Alexios to get his attention so he merges the [PR](https://github.com/spdx/crypto-algorithms/pull/12)

### Next steps

What should we focus attention on after OSS EU?

Agustin: up to OSS EU, I would like to have the following elements merged:
* PR: draft of the list
* [Group Charter](https://github.com/spdx/crypto-algorithms/issues/13): already approved/done
* Attributes [description](https://github.com/spdx/crypto-algorithms/issues/8#issuecomment-3025068280): some review would be welcome
* Current IDs compared to CycloneDX IDs 

Neall and Kate might merge the PR also. If Alexios does not answer by next week, ping the others `ToDo`

### Is a digital signature algorithm a crypto algorithms?

Should we have a signatiure algorithm as a catergory of our list? `Question`

* We have them now as a subcategory of the Assimetric-ket category. We have 4 different subcategories corresponding to DSA, although only one algorithm on the list: dsa
