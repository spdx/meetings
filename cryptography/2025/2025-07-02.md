# SPDX Cryptography Meeting 2025-07-02

## Attendees

* Bob Martin
* Alfred Strauch
* Steven Carbno

## Agenda

* Evaluation of the charter draft
   * Link to the [draft](https://github.com/spdx/crypto-algorithms/issues/13)
* commonkeySize added to the list. Evaluation
   * Link to the [new version of the list](https://github.com/spdx/crypto-algorithms/pull/12)
* Evaluation of the attributes description:
   * Link to the [new version](https://github.com/spdx/crypto-algorithms/issues/8#issuecomment-3025068280)

## Notes

* Charter review approved
* Expression of ranges:
   - Are ranges needed?
      - VaildKey size (yes)
      - Common key sizes (Might not be?)
   - ID, Name, Key size, specify key(? from table)
      - ID and specialized key size as identifier
      - How does CycloneDX define name? Common approach
      - in commonkeySize size is a measure of the difficulty of subverting the cryptographic protection (with classical computers) that is provided by the algorithm and key. ?)
      - in specifiedkeySize size is a measure of the difficulty of subverting the cryptographic protection (with classical computers) that is provided by the algorithm and key. ?)
      - specifiedkeySize would recommendKeySize be better?
