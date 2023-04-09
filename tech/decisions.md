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
| ExternalIdentifier and ExternalReference will be concrete classes which can also be subclassed
| Both line and byte range will be supported in Snippets | 25-Oct-2022 | Only support one due to possible conflict | Tech team minutes 25 Oct 2022 |
| Byte range takes precedence over line range | 25-Oct-2022 | Document would be invalid if byte and line range disagree | Tech team minutes 25 Oct 2022 |
| Profiles are released in sync with spec releases | 4-Oct-2022 | Profiles may be released independently | [Tech Team Minutes 4 Oct 2022](https://github.com/spdx/meetings/blob/main/tech/2022-10-04.md)
| Add NONE to SoftwareDependencyRelationship | 4-Oct-2022 | Keep as is | [Tech Team Minutes 4 Oct 2022](https://github.com/spdx/meetings/blob/main/tech/2022-10-04.md)
| Package Download location cardinality 0..1 | 6 Sept 2022 | cardinality 0..*, Note: If you want to have multiple, create separate element and set relationship to COPY_OF. | Tech Team Minutes 6 Sept 2022 |
| VerifiedUsing should be integrity of thing outside SPDX | 6 Sept 2022 | VerifiedUsing also used for SPDX metadata | Tech Team Minutes 6 Sept 2022 |
| annotation types are REVIEW and OTHER, nothing else for the core | 6 Sept 2022 | Based on prior decisions | Tech Team Minutes 6 Sept 2022 |
| An actor may or may not be tied to an identity | 6 Sept 2022 | Based on prior decisions | Tech Team Minutes 6 Sept 2022 |
| Remove Mandatory Hash from core profile,  and make decision by profile by profile what is expected for integrity. | 11 Oct 2022 | Keep mandatory hash in core | Tech Team Minutes 11 Oct 2022 |
| Add in Curator role to "Identity" as another optional property in 3.0 (context confidence indicator discussion) | 18 Oct 2022 | Defer to 3.1 | Tech team minute 18 Oct 2022 |
| Tool type be clarified and added in 3.1 aligning with efforts from other groups (context confidence indicator based on type of tool used) | 18 Oct 2022 | Implement in 3.0 | Tech team minute 18 Oct 2022 |
| Snippet's location will be defined by byte range and/or line range and byte range takes precedence if there's a conflict | 1 Nov 2022 | See meeting minutes | Finalized tech call 1 Nov 2022, discussed Friday "punchdown" meeting 28 Oct 2022 |
| downloadLocation will only be on Package, external references can be used to add download location to other elements | 1 Nov 2022 | See meeting minutes | Finalized tech call 1 Nov 2022, discussed Friday "punchdown" meeting 28 Oct 2022 |
| homePage will only be on Package and will be singular, external references can be used to add additional links to Packages or to other elements | 1 Nov 2022 | See meeting minutes | Finalized tech call 1 Nov 2022, discussed Friday "punchdown" meeting 28 Oct 2022 |
| packageUrl will only be on Package (no artifactUrl on Artifact), external identifiers can be used to add additional identifiers to Packages or to other elements | 1 Nov 2022 | See meeting minutes | Finalized tech call 1 Nov 2022, discussed Friday "punchdown" meeting 28 Oct 2022 |
| Concept of a content identifier may be added in 3.0 or 3.1 that allows linking a gitoid to different artifacts | 1 Nov 2022 | See meeting minutes | Finalized tech call 1 Nov 2022, discussed Friday "punchdown" meeting 28 Oct 2022 |
| Content identifier will be a property in snippet, file, package, not using external identifier. Gitoid will be the content identifier |  1 Nov 2022 | See meeting minutes | Finalized tech call 1 Nov 2022, discussed Friday "punchdown" meeting 28 Oct 2022 |
| Everyone in between the producer and consumer of the extension should not have to know the schema for the extension | 1 Nov 2022 | Any intermediate tools would need to understand all extension schemas | tech call 1 Nov 2022 |
| ExternalIdentifier and ExternalReference will be concrete classes which can also be subclassed | 8 Nov 2022 | ExternalIdentifier and ExternalReference will be abstract classes which must be subclassed | tech call 8 Nov 2022, Friday call 4 Nov 2022 | tech call 8 Nov 2022, Friday call 4 Nov 2022 |
| Use Relationship Type Other and comment when using an undefined relationship type | Use extensions or add to enumeration values | tech call 8 Nov 2022, Friday call 4 Nov 2022 | tech call 8 Nov 2022, Friday call 4 Nov 2022 |
| Adding to OTHER to hash algorithm enumeration & Comment to Integrity method | keep as is | tech call 8 Nov 2022, Friday call 4 Nov 2022 | tech call 8 Nov 2022, Friday call 4 Nov 2022, tech call 15 Nov 2022 |
| Relationship completeness enumerations "COMPLETE, INCOMPLETE, UNKNOWN" | (other options not captured in minutes) | Tech call 15 Nov 2022 | Tech call 15 Nov 2022 |
| Relationships will be 1 to many type relationships | Many to Many, 1:1 | Tech call 15 Nov 2022 | Tech call 15 Nov 2022 |
| use COMPLETE instead of KNOWN for relationship completeness | Known | Tech call 15 Nov 2022 | Tech call 15 Nov 2022 |
| Optional fields with default values will be handled in serializations | Specify default values in model | Tech call 15 Nov 2022 | Tech call 15 Nov 2022 |
| Standard for how we document model in the repo text files generally follow 2.X RDF format (e.g. capitalization of classes, enumeration prefixes) | See minutes for details | Tech call 6 Dec 2022 | Tech call 6 Dec 2022 |
| Identity - We'll go forward that this version of model, and unless there is a blocker from examples, we'll revisit other issues after 3.0 | Support "BOT" use case better with a "Process" subclass of Entity or Identity, wait for further examples | Tech call 10 Jan 2023 | Tech call 10 Jan 2023 |
| Primary Purpose name will stay as "container" | change to containerImage | Tech call 17 Jan 2023 | Tech call 17 Jan 2023 |
| Identity proposal described in [7 Feb 2023 minutes](https://github.com/spdx/meetings/blob/main/tech/2023-02-07.md#identity-model) | See minutes | Tech call 7 Feb 2023 | [Tech call 7 Feb 2023](https://github.com/spdx/meetings/blob/main/tech/2023-02-07.md) |
| createdBy will have cardinality 1..* | createdBy have cardinality 0..* | Tech call 7 Feb 2023 | [Tech call 7 Feb 2023](https://github.com/spdx/meetings/blob/main/tech/2023-02-07.md) |
| new property createdUsing for tools cardinality 0..* | tools in createdBy | Tech call 7 Feb 2023 | [Tech call 7 Feb 2023](https://github.com/spdx/meetings/blob/main/tech/2023-02-07.md) |
| Tentative decision to keep contentType cardinality at 0..1 | change cardinality to 0..* | Tech call 21 Feb 2023 | Tech call 21 Feb 2023 |
| documentDescribes and hasFiles properties in 2.3 JSON should be deprecated | continue using these "shortcuts" | Tech call 28 Feb 2023 | Tech call 28 Feb 2023 |
| Add back sourceInfo as property to Package | likely an oversight in current draft | Tech call 28 Feb 2023 | Tech call 28 Feb 2023 |
| Keep field name contentType | rename to mediaType | Tech call 7 Mar 2023 |Tech call 7 Mar 2023 |
| add back the suppliedBy property with a range of Agent cardinality 0..1 | use relationship for suppliedBy | Tech Call 21 Mar 2023 | Tech Call 21 Mar 2023 |
| rename the suppliedBy relationship to "availableFrom" who's to property would point to one or more Agents | keep supplied name | Tech Call 21 Mar 2023 | Tech Call 21 Mar 2023 |
| use buildStartTime and buildEndTime | use buildStartDate and buildEndDate | Tech Call 4 April 2023 | Tech Call 4 April 2023 |
