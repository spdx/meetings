## SPDX FuSa Group Meeting - June 16, 2023

## Attendees
* Nicole Pappler
* Maximillian Huber
* Kate Stewart

## Notes

* SBOM types - Kate wants to do a formal mapping of the safety documents and determine which "Type" to classify each artifact in.   Will use the Zephyr documents as a starting point

* TODO:  System BOM diagram for OpenAPS  (note, without safety), but lining up with STPA components.
   * Source --> Build ,  then grouping of Builds into "System".   How to show when different devices are in use. 
   * System -->  set of hardware devices, each of which have a set of software on them.
   * Deploy App "A" on Android Devices
      * Android Deployed SBOM - contains how it was configured, and what runtimes should be available
      * App A - Deployed SBOM - how configured when put on Android Device -->  Depends runtime from Android Deployed SBOM
      * App A - Deployed SBOM --> Depends on  App A Build SBOM  -->  App A Source SBOM
      * Vulnerabilities  --> understand Deployed (component level),   Build --> part assembled inside   Source --> vuln present.  ***Sucessive Filtering*** emerging
      

* Strictdoc - may make sense to work with them on the relationships for linkage
  * https://www.youtube.com/watch?v=k2MCFWvCs7E
  * https://github.com/strictdoc-project/strictdoc-templates
  * https://strictdoc.readthedocs.io/en/stable/strictdoc_01_user_guide.html
  * Strictdoc will enforce mandatory fields.   It's YAML based.
