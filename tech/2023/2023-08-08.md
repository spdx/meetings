# SPDX Tech Team Meeting 2023-08-08

## Attendees
* Adolfo Garcia Veytia
* Andrew Reiter
* Bob Martin
* David Edelsohn
* David Kemp
* Dick Brooks
* Gary ONeall
* Hutch
* Jeff Schutt
* Jennie Kauffmann
* Joshua Watt
* Karsten Klein
* Kate Stewart
* Nisha Kumar
* Peter Monks
* Rob Craig
* Rose Judge
* Sean Barnum
* William Bartholomew

## Agenda
* Continue discussion on blank nodes
* Documentation - William & Alexios
    * Autogeneration
    * Profile overview readiness
* SPDX Documents and Namespaces: https://github.com/spdx/spdx-3-model/pull/403
* Discuss snippetsFromFile property https://github.com/spdx/spdx-3-model/issues/130
* Close on verifiedUsing for packages: https://github.com/spdx/spdx-3-model/issues/345
* Discuss packageFileName https://github.com/spdx/spdx-3-model/issues/83
* Discuss packageFileName issue: https://github.com/spdx/spdx-3-model/issues/83
* Discuss RDF related issues - https://github.com/spdx/spdx-3-model/issues/434, https://github.com/spdx/spdx-3-model/issues/439, https://github.com/spdx/spdx-3-model/issues/438


## Notes
* Blank Nodes - Sean email.
   * Only can do blank notes in serialization (skolomization)
   * Need to specify the recommended approach skolomizaiton. 
   * Specifics of the approach will be refined on Thursday (Serialization).
   * Sean to write up a description of the blank notes, and requires skolomizaton.   Including the recommend approach, as part of a "Draft" PR. 
   * Discussion to be continued in Thursday Serialization meeting. 
   * Jeff:  how are we going to communicate the decisions we've made, and pro's/con's to end users?   
      * Gary:  Serialization directory is the starting point.    Reviewing the draft PR. 

* Documentation
  * William has worked out changes made to Spec parser, and has got it running. 
  * Working to put templates in.   William will send to mailing list as soon as it's ready.
  * Profiles - initial discussion are 
  
* Namespace
   * Separating collection of collection issues - namespace data or just part of format. 
   * Kate has concerns about making sure we can roundtrip and exchange info between collections (SBOMs, documents, etc) as formats. 
   * Assertion of uniqueness, or enforce scope.    Non duplication - "minted collection"?  
   * Reduction by of size of payload is a reason to 
   * Does it need to be solved in the model?    Translate between formats. 
   * Do we need this in the model for 3.0?  or can we do it in 3.1?
   * Clarifying difference between SBOM & SPDX Document.  
   * Serialization should be a separate layer.
   * SPDX NamespaceMap and Document.    Represent at a different place in model? 
      * 1)  Specified in the serialization specification for each specialization, and all serializations must support a NamespaceMap
      * 2) Namespace in ElementCollection  (has been rejected in prior discussion)
      * 3) Put as a property on SPDX Document (which is a subclass of SpdxCollection)
* Next step:  agree on criteria, and then assess between 1 & 3. 
* Understand why it shouldn't be in SBOM, BOM, Bundle...   any collection not tied to specific serialization. 
* Guidance on serialization on how to use it?

## Decisions
* Blank notes need to be skolomized in the serialization. 
* Namespaces: Agree we need to preserve roundtripping and conversion between formats, as well as linkage between elements located in different collections.  (These are criteria)

## Action Items
* Gary to forward profile definitions email from Jordi to Kate

## Next SPDX Tech Team Meeting 2023-08-15
