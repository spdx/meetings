# SPDX Asia Tech Team Meeting 2023-11-20

## Attendees
* Kate Stewart
* Norio Kobota
* Takashi Ninjouji
* Yumi Tomita

## Agenda
* SPDX Lite Profile - sorting through open questions
* Lite Web page on SPDX site - template

## Notes
* Sorting out SPDX Lite PRs
  * https://github.com/spdx/spdx-3-model/pull/523 can this replace https://github.com/spdx/spdx-3-model/pull/521?
     * Kobota-san will talk to Ito-san to look at closing 521
     *  Worked on in OpenChain https://github.com/OpenChain-Project/OpenChain-JWG/blob/master/subgroups/sbom-sg/outcomes/SPDX-Lite/Proposal_v3.0/model/Lite/Lite.md
 https://github.com/OpenChain-Project/OpenChain-JWG/blob/master/subgroups/sbom-sg/outcomes/SPDX-Lite/Proposal_v3.0/model/Lite/Lite-example.json
    * Will add the remainder to 523 after finish discussion in Japan
  * Do you want to enable "dependsOn", or only permit "contains".   Note:  Contains semantic is that it is included in an image. 
     * Following up with Japan,  likely contains is enough. **
  * Root Element property vs. "describes"
     * To denote the root(s) of a tree of elements in a collection, the rootElement property should be used.
     * Raising issue that NTIA requests it with Describes, evolving to use "rootElement" property is expected to be ok.
  
* SPDX-Lite Web Page
   * Need text that follows template like: https://spdx.dev/learn/areas-of-interest/licensing/
   * More examples at https://spdx.dev/learn/areas-of-interest/
   * Need to write out in a document:  Definition;   Personas;  Use Cases;  Benefits
   * Goal - have draft by Nov 29 (so can get moved over),  will be able to update later.

* PackageURL - is it mandatory for LITE?   Discussion decided to use it if proprietary is problematic
