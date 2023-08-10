## SPDX Defects Team meeting Workshop 04.13.2022

## Attendees
* VM Brasseur
* Rose Judge
* Dick Brooks
* Henk Birkholz
* Bob Martin
* Anthony Harrison
* Dick Brooks
* Thomas Steenbergen
* Jeff Schutt
* Karsten Klein
* William Cox

## Agenda: 
* Work out details of outcome of last week's workshop
    * Define text for SWID section 
    * Define text for GitBom section

* Recap of last week workshop

Workshop outcome:

Update https://github.com/spdx/spdx-spec/blob/development/v2.2.2/chapters/external-repository-identifiers.md  with the following new sections:

F.2 Security

It’s recommended practice for SPDX SBOM document creators to include one or more package identifiers (e.g.  CPE, GitBOM, PURL or SWID) when using SPDX external references for the purpose of resolving current security vulnerability information. The specified identifiers are contained in this section, F.2 Security, as well as section F.4.

F.2.1 cpe22Type

F2.3 advisory

Locator Format: URL as defined by  https://www.ietf.org/rfc/rfc1738.txt
Contextual Example:  https://nvd.nist.gov/vuln/detail/CVE-2020-28498
Documentation: A reference to the published security advisory (where advisory as defined per ISO 29147:2018). It may contain an impact statement whether a package (e.g. a product) is or is not affected by vulnerabilities.

F2.4 fix

Locator Format: URL as defined by  https://www.ietf.org/rfc/rfc1738.txt
Contextual Example: https://github.com/indutny/elliptic/commit/441b7428
Documentation: A reference to the source code with a fix for the vulnerability (e.g., a GitHub commit). 

F2.5 url

Locator Format: URL as defined by  https://www.ietf.org/rfc/rfc1738.txt
Contextual Example:  https://github.com/christianlundkvist/blog/blob/master/2020_05_26_secp256k1_twist_attacks/secp256k1_twist_attacks.md
Documentation: A reference to related security information of unspecified type.

 F2.6 SWID

Locator format: URI as defined by https://www.ietf.org/archive/id/draft-ietf-sacm-coswid-21.html#name-uri-schemes.

Conceptual Example: 2df9de35-0aff-4a86-ace6-f7dddd1ade4c

Note: A binary tag-id should be base64url encoded.

External Reference Site: https://csrc.nist.gov/Projects/Software-Identification-SWID

Documentation: [draft-ietf-sacm-coswid-21](https://www.ietf.org/archive/id/draft-ietf-sacm-coswid-21.html#section-2.3)

F4.2 GitBOM

Locator Format: gitoid":"<git object type>":"<hash algorithm>":"<hash value>
Contextual Example: gitoid:blob:sha1:261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64
External Documentation:  https://gitbom.dev/

Note: GitBOM uses a similar algorithm as Git to uniquely identify files by using their 40-byte hash. Gitoid stands for Git Object ID.  Git is an object store, see https://git-scm.com/book/en/v2/Git-Internals-Git-Objects.

## Notes
* Determining SWID reference type specifics:
  * Henk: What if the swid locator is not text? (i.e. bytes?). SWID tag ID can be a 60 byte string that cannot be represented in text but it can be base 64 encoded in a text file.
  * Thomas: We will ad a note to encode base 64 in the spec.
  * Thomas: what value do we want to use for "RefType" keyword? 
  * Henk: `swid` is fine
  * Thomas: SWID locator format? Can we specify this?
  * Henk: Recommendation in swid spec:  https://csrc.nist.gov/Projects/Software-Identification-SWID
  * Thomas: can we link to swid URI scheme: https://www.ietf.org/archive/id/draft-ietf-sacm-coswid-21.html#name-uri-schemes? (Henk confirms)
  * Thomas: Any futher comments on swid?
  * Karsten: trouble with the security type here. SWID is another identifier.
  * Bob: swid is replacement for cpe which is already under "security", so should be consistent with where cpe is now.
  * Jeff: No introduction section to persistent ID. We could add a description and caveats with direction to other identifiers in section F.2. 
  * Thomas: Probably better to put a note in the introduction section F.1 since that is most likely what people will read first. How should we word it? Jeff TODO: will add to the notes.
* Advisory/fix/url: What do we do for the locator format?
  * Dick: you could refer it to the url RFC: https://www.ietf.org/rfc/rfc1738.txt
  * Jeff: you could also use the uri RFC: https://datatracker.ietf.org/doc/html/rfc3986#section-3
  * Bob: 3.0 discussion mostly around URIs
  * Dick: URIs are not always retrievable/downloadable.
  * Rose: Do they need to be? URLs might not be retrievable by everyone all the time (i.e. behind a company firewall) - does it just need to be retrievable by one person?
  * Jeff: maybe constrain to URL for now and we can widen the definition in the future if necessary
* Dick: Concern about "impact statement" in advisory. Term that is used/defined context in research papers but does not really exist in the cyber security world. <agreement to return to this subject later in the meeting>
* Thomas: We need a dedicated security-focused appendix. We could also add to Annex F: "External Repository Identifier". Or, we can just add more examples in Annex F.
* Jeff: how do we provide guidance about security - there has been lots of discussions about this recently.
* Thomas and Anthony: changing the spec will be difficult (if we add an Annex).
* Thomas: bring to tech call that additional guidance is needed. Ask where should we place this and see what they say. We need space for security guidance. 
* Thomas: Option 3 wording - ok to have it in the implemtation guidance?
* Henk: does not prefer implementation guidance in the spec (others agree). Would prefer to have it all in one place.
* Thomas: should we add "option 3 text" (massaged a bit) at the top of the "security" section for appendix F? yes
