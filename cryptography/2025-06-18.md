# SPDX Cryptography Meeting 2025-06-18

## Participants

* Alfred L Strauch
* Victor Lu
* Steven Carbno
* Agustin Benito Bethencourt

## Agenda

* Consolidate the past agreements on the list
* Further discussion about keySize (multiple values)

## Notes

* Agustin is creating a PR.
   * Showed a draft of the list including securityStrength attribute renamed to keySize.
      * Link: https://github.com/spdx/crypto-algorithms/issues/10#issuecomment-2984312012
      * Is it fine like this? No objections
   * Showed a list including the categorization https://github.com/spdx/crypto-algorithms/issues/11#issuecomment-2984366930
      * Is the attribute name cryptoClass correct?
         * No objections
      * How do we include the subcategory?
         * cryptoClass/subcategory is the proposal. No objections
         * Agustin will include the subcategory into the coming PR #task
   * Quique needs to add to ticket #11 the rest of the algorithms.
      * Noted on the ticket
* What do we do with algorithms that has a variable sizes, like min/max or a default and others.
   * What SPDX does when a file has several licenses? Can we use that as an example to solve this question here?
      * References provided to answer that question
         * https://spdx.github.io/spdx-spec/v3.0.1/model/SimpleLicensing/Classes/LicenseExpression/
         * https://spdx.github.io/spdx-spec/v3.0.1/model/SimpleLicensing/Classes/LicenseExpression/
      * Agustin will read these docs and see if we can use it as guidance to solve the above question
* Question about who is sponsoring Agustin's time
   * SCANOSS is sponsoring part of Agustin's time to work on Software Transparency Foundation. The Foundation and SCANOSS agreed for Agustin to invest time here for now.
   * Agustin explains why STF and SCANOSS are interested in standardising how crypto algorithms are declared.
   * Consensus on inviting Microsoft and IBM to these discussions since they might be interested too.
* Agustin was invited to join the SPDX slack channel
