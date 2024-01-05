# SPDX FuSa Group Meeting - October 6, 2023
## Attendees
* Nicole Pappler
* Kate Stewart
* Maximillian Huber
* Stanislav 

#Notes
* Discussion of SPDX example to use for illustrating evidence
* Decision to use: https://renodepedia.renode.io/boards/nrf52840dk_nrf52840/?view=software&demo=blinky. - Blinky could proxy for a warning light, with safety function.
* Target for in europe to have all the evidence pulled together in example for Stan.
* Stan working on example on ReqIF library.   Do a good visualization.   Core elements of a normal document are modeled.   Extend the mapping.   Python library for SPDX.
* Focus on relationships between parent & child - with roles.  
   * Refines, verifies or implements --> link to parent
   * Some cases with child though.
   * Definition of refines...    between requirements and requirements.   Child requirements refine the parent requirement 
* Figure out boundaries between ReqIF and what is represented in SPDX.
* Challenge is ReqIF - defacto supported by tools for exchanging.   XML.   Last updated in 2016
   * look at ReqIF OMG spec - 1.2. - https://www.omg.org/spec/ReqIF/About-ReqIF/
   * Look Prostep organization that has an implmentation guide. - suggesting some updates.
   * https://www.ibm.com/docs/en/engineering-lifecycle-management-suite/lifecycle-management/7.0.0?topic=files-importing-from-reqif - Doors schema - was copied by others. 
   * Implementation
