|Decision|Date|Alternatives|Minutes Link|
|--|--|--|--|
| ExternalMap is a property of Collection | 9-Nov-2021|ExternalMap is only a property of Document | [Tech Team Meeting 9 Nov 2021](https://github.com/spdx/meetings/blob/master/tech/2021-11-09.md)
| Elements are immutable | 19-Oct-2021 | Elements can change after "minting" | [Tech Team Meeting 19 Oct 2021](https://github.com/spdx/meetings/blob/master/tech/2021-10-19.md)
| SPDX-3.0-Model is a new repo | 12-Oct-2021 | Add 3.0 to existing repo | [Tech Team Meeting 12 Oct 2021](https://github.com/spdx/meetings/blob/master/tech/2021-10-12.md)
| DCO for contributions | 12-Oct-2021 | Individual copyrights | [Tech Team Meeting 12 Oct 2021](https://github.com/spdx/meetings/blob/master/tech/2021-10-12.md)
| Logical model uses byte array for hash values | 4-Jan-2022 | various | [Punch list hash](https://github.com/spdx/spdx-3-model/issues/8#issuecomment-1005045081)
| Serialization model defines how to convert byte array to the serialization format | 4-Jan-2022 | Defined in logical model | [Punch list hash](https://github.com/spdx/spdx-3-model/issues/8#issuecomment-1005045081)
| Text-based formats should use a consistent serialization where possible | 4-Jan-2022 | Don't define | [Punch list hash](https://github.com/spdx/spdx-3-model/issues/8#issuecomment-1005045081)
| Text-based serialization would use current text-based serialization | 4-Jan-2022 | Create incompatible format | [Punch list hash](https://github.com/spdx/spdx-3-model/issues/8#issuecomment-1005045081)
| We all agree that signing each individual element is not a requirement | 11-Jan-2022 | Require signing of individual elements | [Tech Team Minutes 11 Jan 2022](https://github.com/spdx/meetings/blob/master/tech/2022-01-11.md)
| We all agree that a set of content with an outer scope needs to be verifiable. (aka document level in 2.2) | 11-Jan-2022 | Make "document level" verification optional | [Tech Team Minutes 11 Jan 2022](https://github.com/spdx/meetings/blob/master/tech/2022-01-11.md)
| in the logical model, there are NO files properties, only CONTAINS relationship between the package and the file | 1-Feb-2022, 8-Feb-2022 | Have only properties, have both properties and relationships | [Tech Team Minutes 1 Feb 2022](https://github.com/spdx/meetings/blob/master/tech/2022-02-01.md)
| Relationships will have a 1 to many relationship between the From element and the To elements | 15-Feb-2022 | Many to Many | [Tech Team Minutes 15 Feb 2022](https://github.com/spdx/meetings/blob/main/tech/2022-02-15.md)
| Agreement to add comments back to external reference | 1-Mar-2022 | Remove comments from external reference | [Tech Team Minutes 1 Mar 2022](https://github.com/spdx/meetings/blob/main/tech/2022-03-01.md)
| Signatures fall under integrity, but not considered blocking |  1-Mar-2022 | Signatures part of core | [Tech Team Minutes 1 Mar 2022](https://github.com/spdx/meetings/blob/main/tech/2022-03-01.md)
| details of a subject can go into a profile | 15-Apr-2022 | details in core | [SPDX 3.0 Model Session - April 15, 2022](https://github.com/spdx/meetings/blob/main/tech/2022-04-15-model-session.md)
| SpecVersion property will be a string that is constrained to one of a set of canonical options published by SPDX in the current or any future specifications | 17-May-2022 | Structured property, subset of SemVer in spec | [Tech Team Minutes 17 May 2022](https://github.com/spdx/meetings/blob/main/tech/2022-05-17.md)
| SPDX-Snippet-Begin and SPDX-Snippet-End used to mark snippets in source files | 6-Jun-2022 | SPDX-Snippet-Begin: ID/Name ... | Tech Team Minutes 7 Jun 2022
| Remove version from profile property | 4-Oct-2022 | Each profile has a version property | [Tech Team Minutes 4 Oct 2022](https://github.com/spdx/meetings/blob/main/tech/2022-10-04.md)
| Profiles are released in sync with spec releases | 4-Oct-2022 | Profiles may be released independently | [Tech Team Minutes 4 Oct 2022](https://github.com/spdx/meetings/blob/main/tech/2022-10-04.md)
| Add NONE to SoftwareDependencyRelationship | 4-Oct-2022 | Keep as is | [Tech Team Minutes 4 Oct 2022](https://github.com/spdx/meetings/blob/main/tech/2022-10-04.md)
| Package Download location cardinality 0..1 | 6 Sept 2022 | cardinality 0..*, Note: If you want to have multiple, create separate element and set relationship to COPY_OF. | Tech Team Minutes 6 Sept 2022 |
| VerifiedUsing should be integrity of thing outside SPDX | 6 Sept 2022 | VerifiedUsing also used for SPDX metadata | Tech Team Minutes 6 Sept 2022 |
| annotation types are REVIEW and OTHER, nothing else for the core | 6 Sept 2022 | Based on prior decisions | Tech Team Minutes 6 Sept 2022 |
| An actor may or may not be tied to an identity | 6 Sept 2022 | Based on prior decisions | Tech Team Minutes 6 Sept 2022 |

