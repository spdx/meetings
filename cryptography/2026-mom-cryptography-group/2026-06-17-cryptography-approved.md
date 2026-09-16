# SPDX Cryptography Meeting 2026-06-17

###### tags: `ToDo` `Question` `Agreed`

:::info
- **Where:** Remote through [Jitsi](https://meet.jit.si/SPDXCryptoMeeting)
- **When:** Every Wednesday at 15:00 UTC for 30 minutes
- References:
   - Past [MoMs](https://github.com/spdx/meetings/tree/main/cryptography)
   - SPDX Cryptogrphic Algorithms [list](https://github.com/spdx/cryptographic-algorithm-list)
- Approved: 2026-06-24

---

## Attendees

* [ ] Bob Martin
* [x] Alfred Strauch
* [x] Steven Carbno
* [x] Agustín Benito Bethencourt
* [ ] Quique Goñiz


## Agenda

1. Approval MoM that took place on 2026-06-10
2. How to express parameters: mode
3. Tech team

:::

## MoM

### Approval MoM that took place on 2026-06-10

* Please find the [MoM](https://hackmd.io/cCAYb1hwSgOu0iBAcCYjvQ)

* [x] Approved unanimously 

### How to express parameters: mode

These are the two proposals following Steven's and Agustin's approach. Both are described in thecomments section of the [Issue#39](https://github.com/spdx/cryptographic-algorithm-list/issues/39)

1. Steven's approach [link](https://github.com/spdx/cryptographic-algorithm-list/issues/39#issuecomment-4671066231)
    * His original description of AES [link](https://github.com/spdx/cryptographic-algorithm-list/issues/39#issuecomment-4568868020)
2. Agustín's approach [link](https://github.com/spdx/cryptographic-algorithm-list/issues/39#issuecomment-4729411247)
3. Comparisson algorithm per algorithm of the 32 algorithms selected [link](https://github.com/spdx/cryptographic-algorithm-list/issues/39#issuecomment-4729697357)

#### Comparison by Agustin (bias)

* Both proposals were applied to the same 32 algorithms across six families (15 block ciphers, 4 stream ciphers, 4 hashes, 1 MAC, 1 checksum, 2 password-hashing/KDFs, 3 public-key, 2 key-exchange).
* Steven's proposal uses a single generic shape — a `parameter:` list where every entry is an object with `name`, `description`, `type`, `cardinality`, `values`. The schema is uniform across all parameters. The semantic meaning of each parameter lives as free text inside `description`, repeated in every YAML that uses that parameter.
* Agustin's proposal uses a typed taxonomy: each parameter has its own name and structure, defined once in the properties description file. The YAML files carry only data — names of parameters and their values.
* Steven's strengths:
   * Self-contained/documenting .yaml files
   * Uniform schema across all parameters
   * No additions to the description file
* Agustin's strengths:
   * Single source of truth for parameters. Consistency
   * .yaml remain typed and concise
   * Maintainability

#### Discussion

* After describing the proposal and discussing some inconsistencies and potential corner cases, and given that we do not agree on which approach to take, Agustin suggested to go for Steven proposal and see how far we get with that approach.
   * Steven will create a PR for two algorithms so we have a couple of example of how to express openrationMode `ToDo`
   * We will go one parameter at a time
* Alfred suggested to involve the tech team before consolidating the decision.
   * Let's contact the tech team with a summary of were we are. `ToDo`
   * Ask for a slot during their meeting to provide a presentation on the two proposals `ToDo`
