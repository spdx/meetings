# SPDX Tech Team Meeting 2023-10-17

## Attendees
* Alexios Zavras
* Bob Martin
* David Edelsohn
* David Kemp
* Gary O'Neall
* Joshua Watt
* Maximilian Huber
* Nisha Kumar
* Rob Craig
* Rose Judge
* Sean Barnum

## Agenda
* Gary/Sean/David/Jeff/Nisha - Follow-up from Serialization meeting
  * Decide on logistics for the next serialization meeting
* Review / approve / merge outstanding RC2 non-serialization PR's is:open is:pr milestone:3.0-rc2 -label:serialization -label:wontfix 
* Review / assign outstanding RC2 non-serialization issues - review in reverse order: https://github.com/spdx/spdx-3-model/issues?q=is%3Aissue+is%3Aopen+milestone%3A3.0-rc2+-label%3Aserialization+-label%3Awontfix+sort%3Acreated-asc+

## Notes
* Build profile wants restrictions on relationshipType
  * BUILD_TOOL, CONFIG_OF are subset of INPUT_OF
  * https://github.com/spdx/spdx-3-model/issues/515
  * constrained in model "shape"
  * How the spec can require one of the three.
  * Additionally outputOf and invokedBy
  * mixup between Build/Build.md (namespace description) and Build/Classes/Build.md (class description)
  * another restriction that a Build object MUST exist for Build profile to pass its conformance point
* Reviewed/ Approved/ Merged PRs
* Focused on reducing the number of relationships in the build profile while maintaining comprehensive tracking.
* A specific constraint with the input-off relationship type was discussed, along with the possibility of build-to and constraints-off serving as inputs to a build.
* Team explored ways to define constraints on the relationship type property and the value of the relationship type itself.
* Touched upon how to represent external relationship constraints and constraints on relationship types at the implementation level.
* The need for defined relationships on the 'build' class, not on the namespace description, was highlighted.
* The discussion continued on how to express conformance points for external relationships in the build profile.
* The group reviewed previous pull requests and discussed current constraints and the alignment with the security profile group, in addition to considering Python for the task.
* The meeting discussed limitations of conformance points, the need for documenting restrictions, serialization progress, and the potential of defining a specific type of URI for element ID.
* The addition of a data type that offers clarity on what it represents was proposed.
* The External Identifier and External ID properties were discussed, and renaming for these properties was suggested.
* The possibility of a major redesign due to generalization and the renaming of certain properties from within SPDX were discussed.
* Other topics such as removing data licenses from creation, relationship restrictions, update security, and PSS support were also touched upon.
* The need to update the readme file to reflect current changes in the generated files was mentioned.

## Reducing Relationships and Defining Constraints in Build Profile
* The initial addition of numerous relationships in the build profile intended for later reduction.
* Nisha mentioned the complexity of describing some constraints like input-off, build-to and constraints-off in the specification.
* Discussion on defining constraints on relationship types was led by Sean Barnum.
* Nisha clarified the need for constraints on relationship types which are part of a repository.
* Discussion on external relationship constraints and their representation in the specification.
* Reminder by Maxabout the current focus on the model level and the need to move to implementation level discussions.
* Alexios suggested defining the relationships on the build class, not on the namespace description.

## Expressing Conformance Points for External Relationships
* Alexios initiated the discussion about defining the focus and restrictions for conformance points.
* Review of a previous pull request dealing with similar constraints was done.
* Suggestion: checking the comments in the issue related to the flight profile.
* Nisha found a comment that described external relationship restrictions with a relationship type and from type.
* Sean confirmed that constraints were only for the type, not specific objects.
* Discussion about aligning with the security profile group's solutions for similar constraints was initiated by Alexios.
* Nisha suggested a new constraint involving the existence of a build class and certain relationship types to the lifecycle class.
* Suggestion: Use Python for typing constraints was discussed with approval

## Documentation of Restrictions for Conformance Points
* Sean and Alexios planned to meet to discuss the form and documentation of the conformance point.
* Alexios proposed to open a new issue to document the different restrictions for conformance points.
* Discussion about possible restrictions like the need for an element of a particular class and a relationship point of a specific type.

## Progress on Serialization and Discussion on Pull Requests
* Updated about the ongoing work of the serialization team and the existing two proposals.
* Discussion about some undecided points in the serialization model.
* Older pull requests were reviewed with the hope of merging some soon.
* Discussion about defining a specific type of URI that would serve as an element ID was led by Sean Barnum.

## Changes to External Identifier and External ID Properties
* Sean proposed the addition of a data type that would serve as a subset of all strings for clarity.
* Discussion about renaming External ID property to avoid confusion with External Identifier.
* Suggestion of renaming the External ID property to either External SPDX ID or Externally Defined SPDX ID, and External Identifier to External Non-SPDX Identifier.
* An agreement to update the pull request with the new names before RC2 was suggested by Gary.

## Decisions
* decision on externalId recorded in  https://github.com/spdx/spdx-3-model/pull/492
* Proposed the addition of a data type that would serve as a subset of all strings
* Agreed to update issue to version 3.1 where it would not change their validation
* Renaming External Identifier to External Non-SPDX Identifier
* Renaming External ID property to either External SPDX ID or Externally Defined SPDX ID

## Action Items
* Alexios to create a new issue related to "conformance points" of namespaces, detailing different restriction types
* Discuss conformance point with Alexios
* Open a new issue to document restrictions for conformance points
* Update the file for the task on Python constraints
* Document all restrictions necessary for conformance points
* Decide on representation of physical collection within the STDxDocument
* Propose a specific type of URI for element ID
* Define data types that could provide clarity on representation
* Rename External ID and External Identifier to reduce confusion
* Update the current pull request with the new names for External ID and External Identifier property
* Update the readme file to reflect changes in state of generated files

## Next SPDX Tech Team Meeting 2023-10-24
