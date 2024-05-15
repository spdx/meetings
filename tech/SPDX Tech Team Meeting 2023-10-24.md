# SPDX Tech Team Meeting 2023-10-24

## Attendees
* Alexios Zavras
* Bob Martin
* David Edelsohn
* David Kemp
* Jeff Licquia
* Jeff Schutt
* Joshua Watt
* Karsten Klein
* Matt Rutkowski
* Nisha Kumar
* Peter Monks
* Rob Craig
* Rose Judge
* Sean Barnum
* William Bartholomew

## Agenda
* Profile conformance restrictions (Alexios)
* Yocto Serialization Questions/Comments (Joshua Watt)
* GitHub open issue review

## Notes
https://github.com/spdx/spdx-3-model/issues/522
* "Profile" used to represent namespace, team, and set of restrictions
* Need to describe the types of restrictions that can be applied
* An example: profile can make "name" required on element
* Some restrictions cross multiple elements
* Suggestion: Use plain English to describe restrictions for now, and use formal language post RC2, maybe post 3.0
* Example: `model/Licensing/conformance.md`
* Some constraints (pun intended) on the conformance statements should be imposed so we don't create requirements that can't be implemented later
* Use the PR review process to sanity check
* Question: Should constraints be contextual (i.e. on class)?
* Not mutually exclusive
* For classes, properties, etc. that are specific to a profile you can describe the constraint there, spec-parser will aggregate a list of constraints for a profile
* Decision:
* If a constraint applies to a single class or property defined in the profile, then the constraint can be described in the markdown for the class or property (a process that Security and Build is already using)
* If a constraint applies to multiple classes or properties, or applies to a class or property outside of the profile, then it will be described (in English) in `conformance.md` in the root of the profile
* Yocto Serialization Questions/Comments
* Example of linking to CVEs (was looking in `examples` folder)
* Look at the examples in the Markdown files in `model/Security`
* Where is filename now?
* element.name
* Can there by multiple root elements? Use ElementCollections a lot
* Yes
* Request: It would be helpful if the comments for the relationship types were put in the model output (model.json)
* Suggested opening an issue for spec-parser
* Primary purpose for root file system
* OS suggested, it was felt that should include kernel
* They would call it "IMAGE"
* Suggestions: "FILESYSTEM", "DISK_IMAGE"
* Relationship fanout
* Some relationships felt backwards, example was license that applies to source code (3000 files with the same license)
* Suggestion: Make sure the text on the relationships (and/or the relationship name) makes the directionality clear. Also need to flag relationships that are bidirectional. Every description should mention `from` and `to` to make the relationship source and destination clear.
* Suggestion: Allow collections to be empty.
* For example, query result where the query didn't match anything.
* Not blocking anymore.
* Suggestion: Collection be element `0..*`.
* Decision: Root elements should should be 0..* not 1..*
* Suggestion: Document the use case for having an empty `to` on relationships.
* What's not in the model is the data types
* Example: SemVer, MediaType, etc.
* Suggestion: Include in model information to help generate these.
* No class for Extension
* This is in a PR
* SemVer regexp
* Don't know what dialect this is
* Python didn't understand it
* Suggestion: Explicitly state a dialect in the spec
* Possibility: Markdown rendering broke it
* LicenseListVersion
* Supposed to be SemVer but doesn't have the third part
* SemVer regexp didn't match
* Suggestion: We either need to change the data type or change license list versions to be semver (i.e. add third part)
* Do you need to have Context in Json LD files, or can you have Context-free? i.e. full IRIs
* Yes, we're currently not using Context for anything else.
* PyLD struggled with vocab prefixes and things that weren't 1:1 mapping
* Validator
* Didn't handle @graph, blank nodes, referencing by string
* GitHub issue review
* https://github.com/spdx/spdx-3-model/issues/493
* Suggestion: Use packageUrl not purl to avoid confusion with Persistent Uniform Resource Locators
* Backwards compat says use `purl`
* Avoiding confusion says use `packageUrl`
* Either way, we should pick ONE

## Action Items
* Create a pure text file to describe conformance points
* Review conformance statements using the PR review process
* Open an issue in the spam pods repo to discuss including comments or relationship types in the model
* Raise an issue regarding automated validation of profiles
* Raise an issue about describing data types in JSON-LD
* Raise an issue regarding mismatched SemVer regex and licence list version
* Raise an issue about issues with the JSON-LD tool struggling with vocab prefixes and anything that wasn't a one-to-one mapping
* Try SpecParser to make SPDX validator happy with the documents produced
* Provide a build profile example for YACTO project
* Open an issue in the repo for validated tools to address the issue with SPDX validator

## Decisions
* Using lay language to express restrictions for conformal profiles.
* Constraints should be documented in the most relevant markdown file.
* The PR review process will be used to review conformance statements.
* One place should be reserved to collect all the constraints defined outside of the profile.
* To use "software artifact" instead of "software element".
* Use "has concluded license" instead of "concluded license" and allow empty collections.

## Next SPDX Tech Meeting 2023-10-31
