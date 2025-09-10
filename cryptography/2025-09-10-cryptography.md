# SPDX Cryptography Meeting 2025-09-10

###### tags: `ToDo` `Question` `Agreed`

:::info
- **Where:** Remote through [Jitsi](https://meet.jit.si/SPDXCryptoMeeting)
- **When:** Every Wednesday at 14:00 UTC for 30 minutes
- References:
   - Past [MoMs](https://github.com/spdx/meetings/tree/main/cryptography)
   - Crypto algorithms [list](https://github.com/spdx/crypto-algorithms)

## Attendees

* [ ] Bob Martin
* [ ] Alfred Strauch
* [x] Steven Carbno
* [x] Agustín Benito Bethencourt
* [x] Quique Goñiz
* [x] Jean Camp


## Agenda

1. News
2. Expressing several values on a property
3. Expressing ranges on a property
4. AOB

:::

## MoM

### News

* Talk at OSS EU 2025 referencing the list. [Video](https://www.youtube.com/watch?v=ULNpaeLJjvY)
* Asked Alexios about how should I let him know about the need for him to review back the PRs where comments has been addressed
* Next PR is ready, which fixes [Issue 18](https://github.com/spdx/crypto-algorithms/issues/18#issuecomment-3274792866)

### Expressing several values on a property

Reference: [issue 16](https://github.com/spdx/crypto-algorithms/issues/16)

The example expresses what we agree on. Now create a PR with these changes: `Agreed`
1. One PR adapting the List properties description
2. One PR adapting the list elements

### Expressing ranges on a property

* Mail [sent to spdx-tech](https://lists.spdx.org/g/Spdx-tech/message/5991) asking for options there.
* Agustin sent the mail also as a test to see if this mailing ilst provides help.
* The participants could not think of a reference in SPDX to help us solving this question 
* Maybe using something in the line of min,max value or upper/lower limit could be the way to go

### AOB

* Steven. What if we create a template for the list elements as a educational material ?
   * We can create a fake crypto algorithm described including all the properties and options and call it template
   * The particiants think this proposal from Steven can be useful for onboarding `Agreed`
* Jean. Should we have an itar compliant flag? `Question`
