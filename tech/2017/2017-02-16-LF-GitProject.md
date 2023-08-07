Feb. 16, 2017

## Linux Foundation Leadership Summit – Git Integration Discussion

## Discussion Outcomes

  - Git Plugin scoping - resulting in a project idea(s) for integrating
    SPDX with GIT for the purpose of increased SPDX document adoption
  - Review and refinement of the overall tools project ideas page

## Git Plugin scoping

  - Primary target user: code originator
  - Purpose: Generate SPDX documents using existing API's or hooks
  - Objectives: Developer tool, visibility, generation, "anyone can do
    it"
  - Produces: Valid SPDX documents
  - Use existing API's
  - Git API or GitHub API?
      - Git API covers more usage (local, server, several services)
      - GitHub API - more visible
      - Git API only at commit level - too granular
      - Agree to pursue GitHub API so that we can do by release rather
        than at commit level
      - Roll-up per file license information based on SPDX license ID
        included in the files
          - Optionally do some parsing of the source files for
            license/copyright info
  - Can also be used for a "score" of license compliance (although there
    is a separate proposal for scoring)
  - Package level information can be provided through a mechanism to be
    decided (it could be a metafile like .spdx or an SPDX document with
    package only information, or perhaps a UI)
  - Would be triggered on a build

## Other tools project ideas

  - build related tools
      - Yocto - several tools already, but we need package
        relationships. Tools under development, but there is scope for
        an additional project idea
      - Maven - existing tool which could be leveraged
      - MSBuild - Would be worth exploring
      - PIP - Would be worth exploring
      - DEB - High usage, would be worth exploring
      - NPM - Uses license ID's, but does not yet produce SPDX docs -
        would be worth exploring
      - Others we may explore in the future - Gradle, Ivy, C/C++/Make,
        Other languages
  - Online validation and other online tools
  - Summary tools that target different audiences (e.g. legal) a.k.a.
    "viewers"
  - Transparence/Scoring
      - Command line tool to score license compliance based on the
        license information in files
      - Goal: Improve the license compliance information in the files
      - Approach: Pseudo code -\> tool
      - Features: Ability to identify files that are deficient

[Minutes](Category:Technical "wikilink")
[Category:Minutes](Category:Minutes "wikilink")
