# SPDX Tech Team Meeting Translation 2024-06-06

## Attendees

- Jeff Licquia
- Gary ONeall
- Alexios Zavras
- Arthit Suriyawongkul

## Agenda

- Internationalization/localization structure/process for spec and for model

## Notes

- Following discussions in 2024-05-28 Tech team meeting and emails
  - https://github.com/spdx/meetings/blob/main/tech/2024/2024-05-28.md
  - https://github.com/spdx/meetings/blob/main/tech/2024/2024-05-28-i18n-examples.md

### Spec repo
- Spec
  - Currently, a branch per version, only in English
  - OpenChain - preference was to have a separate repo / their own setup for the translated languages
    - Allowed for issues to be written in local language / separate tracking of issues
    - Consumers of the spec may be more comfortable in the local language
  - For the spec, separate repo would be too difficult
  - Plugin supports directory per language and file per language
  - Options for Spec:
    - branch per version/language
    - branch per version, directory per language
    - branch per version, file per language
  - Translation process - how do we track what has changed and make sure the translations are current
    - Easier to translate shorter strings
    - Git provides commands to identify modificiations
    - Could also be done through file modification times
    - Easier from single branch
- How do we tag different releases?
  We may release the English version of the spec followed by other languages.
  - Proposal - tags - 3.0.1 for the English, tags for additional languages (e.g. 3.0.1-JA)
  - 
- Decision - Single branch for developement and branch off for release
  - Supports translations since changes can be made to the relese branch
- Decision - for spec - directory approach
- Decision - move the current docs text under docs/en
- Example:
```
docs/
en/
annexes/
introduction.md
ja/
annexes/
introduction.md
```
- Note: each version has its own workflow script, so we can have a different generation for each release
- Proposal to only worry about 3.0.1
- We have Chinese translation for v2.3 - what to do with it in this new structure?

### Model repo
- The generated model markdown files would be put in the spec repo using the above agreed to directory structure
- Repo per language requires no effort on the spec-parser
- Repo per language requires a bit more complexity on the spec GitHub action
  - would need to checkout each of the repos and run spec parser
- Snippet approach was preferred by Arthit and Gary, Alexios will look into the impact on the spec-parser

## TODOs:
- switch to release branch
- restructure repo for the language subdirectories
- implement mkdocs language plugin
  - https://github.com/ultrabug/mkdocs-static-i18n
- Alexios will investigate the spec parser impact of the snippet approach for the model
- We'll decide on the model repo approach on Tuesday's call
- Gary will review the decisions and minutes with the Asia team on Monday
