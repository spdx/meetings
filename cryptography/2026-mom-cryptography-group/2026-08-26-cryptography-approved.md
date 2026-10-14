# SPDX Cryptography Meeting 2026-08-26

###### tags: `ToDo` `Question` `Agreed`

:::info
- **Where:** Remote through [Jitsi](https://meet.jit.si/SPDXCryptoMeeting)
- **When:** Every Wednesday at 15:00 UTC for 30 minutes
- References:
   - Past [MoMs](https://github.com/spdx/meetings/tree/main/cryptography)
   - SPDX Cryptogrphic Algorithms [list](https://github.com/spdx/cryptographic-algorithm-list)
- Approved: 2026-09-02

---

## Attendees

* [x] Bob Martin
* [x] Alfred Strauch
* [x] Steven Carbno
* [x] Agustín Benito Bethencourt
* [ ] Quique Goñiz


## Agenda

1. Approval MoM that took place on 2026-08-11
2. News
3. pqcClass

:::

## MoM

### Approval MoM that took place on 2026-08-11

* Please find the [MoM](https://hackmd.io/V42amFzSTze699cqL0GfEw)

* [x] Approved unanimously 

### News

* Proposal sent to the cryptographers through mail
* New issue related with PQC Algorithms parameters [Issue#88](https://github.com/spdx/cryptographic-algorithm-list/issues/88)
    * This ticket is a byproduct of maturing [Issue#73](https://github.com/spdx/cryptographic-algorithm-list/issues/73) 
* Two pending todos from the 2026-08-11 [MoM](https://hackmd.io/V42amFzSTze699cqL0GfEw) 
* SPDX 3.1 RC2 coming on september

### pqcClass 

* Agustin polished [the current proposal](https://github.com/spdx/cryptographic-algorithm-list/issues/73#issuecomment-5267793501) 
   * Improvements in the property pqcClass description
   * Additions of parameters and values on each of the candidate algorithms, for completeness. Included some comments that called my attention
       * Worth noting that we have another example here of an algorithm that fits into two different cryptoSubClass values: sqisign 
   * Interesting case of mceliece and classic-mceliece (PQC). It would be good to confirm the proposal on this point

#### There is no accurate `cryptoSubClass` for a KEM

Currently

`cryptoClass "Asymmetric-Key-Algorithm"
    cryptoSubClass values: "Public-Key-Encryption" , "Public-Key-Cipher" , "Elliptic-Curve-Cryptography" , "Digital-Signature" , "Protocol", "Hybrid-Cipher" or "Key-Exchange-Mechanism"`


Four of the ten candidates are Key Encapsulation Mechanisms. The available value is `Key-Exchange-Mechanism`. These are different things. A KEM encapsulates a random shared secret under a public key. A key exchange is an interactive protocol between two parties.

Options:

* Add `Key-Encapsulation-Mechanism` as a new value in issue [Issue#72]()
* Reuse `Key-Exchange-Mechanism` and accept the inaccuracy.
* Reuse `Public-Key-Encryption`, which is closer mathematically but hides the KEM role.

The first option is the accurate one. It should be raised in #72 now, because four PQC entries depend on it. We should not add the candidate algorithms without addressing this point

#### Stateless vs stateful

`pqcClass`: `Hash-Based`. SLH-DSA is stateless. The stateless versus stateful distinction has no property today. It matters a lot in practice, because stateful schemes break if state is reused.

#### oid for PQC algorithms

The List describes algorithms. OIDs describe parameter sets.

ML-KEM has no single OID. It has three. SLH-DSA has twelve, or twenty-four counting pre-hash modes. Classical entries such as `rsa` carry one OID for the whole algorithm.
* ml-kem
    * oid:
      - 2.16.840.1.101.3.4.4.1
      - 2.16.840.1.101.3.4.4.2
      - 2.16.840.1.101.3.4.4.3
    * `oid`: NIST registered one OID per parameter set, not one for the algorithm. The three OIDs above are `id-alg-ml-kem-512`, `-768` and `-1024`.
* SLH-DSA
    * oid:
      - 2.16.840.1.101.3.4.3.20
      - 2.16.840.1.101.3.4.3.21
      - 2.16.840.1.101.3.4.3.22
      - 2.16.840.1.101.3.4.3.23
      - 2.16.840.1.101.3.4.3.24
      - 2.16.840.1.101.3.4.3.25
      - 2.16.840.1.101.3.4.3.26
      - 2.16.840.1.101.3.4.3.27
      - 2.16.840.1.101.3.4.3.28
      - 2.16.840.1.101.3.4.3.29
      - 2.16.840.1.101.3.4.3.30
      - 2.16.840.1.101.3.4.3.31

    * `oid`: twelve pure-mode OIDs, one per parameter set, plus twelve more for the pre-hash modes (`2.16.840.1.101.3.4.3.35` to `.46`).
        * Listing 24 OIDs in one entry is possible with cardinality [0..*], but it is not readable. 

Options:

* Accept long `oid` lists. Simple, but unreadable and hard to use for detection tools.
* Create one entry per parameter set. Accurate, but it multiplies the List by ten and breaks the "one algorithm, one entry" model.
* Add a structure that binds each OID to a parameter set. More work, and it interacts with the deferred parameters decision.

Idea: 
ABNF 
CryptographyAlgorithmName = Algorithm-id / Algorithm-id Algorithm-Parameters
Algorithm-id = <short form identifier from SPDX CryptographyAlgorithm List>
Algorithm-Parameters = *( "-" Algorithm-Parameter / "-" Algorithm-Parameter-Set ) ["-*"]
Algorithm-Parameter-Set = "[" Algorithm-Parameter *( "|" Algorithm-Parameter ) "]"  
Algorithm-Parameter = <The Nth CryptographyAlgorithm Parameters Value from SPDX CryptographyAlgorithm List> 
    
Example: https://oid-base.com/get/2.16.840.1.101.3.4.3.20
    
The inmediate solution could be to relax the current one-alg - one-iod principle and allow multiple oids per algorithm, when the parameters discussion comes to place.


#### commonkeySize vs specifiedkeySize

pqcClass and the new associated algorithms challenges uor current commonkeySize vs specifiedkeySize usage. Currently commonkeySize and specifiedkeySize are used inconsistently. PQC algorithms exacerbate these inconsistencies.

