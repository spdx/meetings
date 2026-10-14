# SPDX Crypto List meeting 2025-05-21

* Date: 2025-05-21
* Time: 14:00 UTC
* Video chat link: https://meet.jit.si/SPDXCryptoMeeting

## Participants

* Steven Carbno
* Alfred L Strauch
* Agustin Benito Bethencourt

## Agenda

* Categorization
* Discussion about security securityStrength
* Ticket status

## Discussions about the categorization

- Can we go first for the basic categorization?
   - Cryptographic hash functions
   - Symmetric-key algorithms
   - Asymmetric-key algorithms
- Open a ticket about this discussion

## Considerations about the securityStrength

- Standardization bodies provide recommendations based on strength, together with the lifetime value, which means that this is an interesting attribute
- These are values that change overtime.
- The existing values are based on what has been detected. They are solid although they might change overtime. There can be others too.
- Task: open a discussion on a ticket about how to handle these attributes, which are important but might change overtime.

## Discussion about the tickets

* https://github.com/spdx/crypto-algorithms/issues/8
   * No discussion.
* https://github.com/spdx/crypto-algorithms/issues/9
   * The idea is good. We need to consider some of the hard cases like what happens when there is no origin. We should discuss it more.
   * Agustin explained that in some cases, finding the origin is straight forward. In others it is not.
   * Can we add just those which are clear as starting point?
