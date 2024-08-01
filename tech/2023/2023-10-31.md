# SPDX Tech Meeting 2023-10-31

## Attendees
* Gary O'Neall
* Kate Stewart
* Rob Craig
* Jeff Licquia
* Sean Barnum
* Joshua Watt
* Matt Rutkowski
* Rose Judge
* Nisha Kumar
* Karsten Klein
* Max Huber
* Peter Monks
* Dick Brooks

## Agenda
* Update and discussion from the Serialization Team
* Update on Documentation Generation
* Describes Relationship vs. Root Element Property

## Notes

## Serialization
  * Implementation issues with JSON-LD - resulted in lots of additional meetings over last couple of months.
  * Separate physical "SPDXDocument" from logical "SPDXDocument"
  * One and only XCollection within a serialized file.    
  * In a physical file, can only have one SPDXDocument/XCollection in it.
* Discussion on External Map Issue in SPDX 3.0
  * SPDX 3.0 - ExternalMap is used to reference components outside current document. 
* Nisha highlighted challenges in referencing SPDX elements defined outside of serialized files.
* Gary stated that the external map would be retained as an optional field.
* Sean offered help to provide real-life examples.
* Nisha suggested sharing a collection of documents on external references rather than a single example.
* Alternative proposal could be introduced as an additional mechanism.
* Need to test ExternalMap with real world scenarios.    Using ExternalDocumentRef
* Looking for examples to experiment with:   
* https://zephyr-dashboard.renode.io/ - Sean looking at reference example. (Nisha will send Sean an example)
* Maven example - Gary to look at https://github.com/spdx/spdx-examples/tree/master/software/example8
* Yocto example - Joshua used.   Somewhat problematic.  IRIs should minimize this. 
* Work on in parallel with RC2 meeting
* Consumer of serialized file, look and see wrapper for the element collection (ie. XCollection is a special instance of element collection).
  * Name for XCollection?
     * SPDX Document - compatible, with unique type name,  has already been represented in different types. Properties can be mapped to 2.3 implmentation.   Negative: 
     * Serializable Collection
  * What does it mean to have a collection that is not serializable? No, not implying others can't be serializable.   Key is what is the purpose of defining a collection. It is an element collection intended to have a shared context. 
* Use cases for XCollection
   * Creator wants to sharing 47 elements with another entity
   * Must include all serialization information inside it, such as actually creating a file, recording root element, and where to start; and using XCollection to define unique name for file it is about. 
   * Receiver might want to retain logical information about a file you've deserialized.  (ie. Translation tool info ) like namespaces and logical elements
* Consideration:  First thing that someone recieves - so it needs to be clear.   Keep consumers in mind. 
* Sean has concerns about using the same name where semantics have been clarified from both physical and logical;  to just logical
* Joshua:  Defining document? Gary:  changes to be refering to physical artifact and location.   Same class as a source file, not referring to XCollection.   New relationship between XCollection and Artifact?  Logical form of what I'm serializing -->. serializing in different artifacts. 
* Sean:  SBOM, Package, File.  Same set of logical content.  Each serialization would contain the collection element, and would have an artifact (with related hash), but could all be related back to the same logical.  XCollection would have the same globally unique id.   Assertion that reproducible build breaking.
* Gary.  More about logical than physical today.   So not sure that SPDX Document will be confusing.
* Karsten: Like concept of an assertion with that semantics
* Peter: Mostly work with casual users,  just want to construct and be done.   Serialized collection would be hard to explain.  SPDX Document is an easier term to explain.
* Dick: +1 on SPDX Document as a well understood term. 
* Sean: What it is historically is different to what it is in 3.0;    not the creation of the file, but content of the file.   See that will cause confusion; but fine with making it clear.   
* Peter: Make it as easy as possible, as it doesn't open door to further questions.   Folks want to learn more, want more specificity would want to learn more.
* Nisha: Users want a too that spits out a file. 

## Ask review of PRS - in next week
PR to document how we serialize data which may be implemented in the native serialization      format: https://github.com/spdx/spdx-3-model/pull/509        
PR to update the External Map to use Artifact and relationships to the “XCollection”: https://github.com/spdx/spdx-3-model/pull/542        
PR to document the “XCollection”: https://github.com/spdx/spdx-3-model/pull/490  
Note: they all need to be updated with the agreed upon name  

## SPDX Document Naming and Document Generation Updates
* William has cleaned up Python housekeeping in last week.   Not a blocker.   Will be update from that.
* Tentative decision to keep the term 'SPDX document' but pending feedback from William and others.
* Jeff updated about document generation and need to sync up with Alexios and William on spec parser.
* Discussion on usage of 'describes' relationship in an element collection.
* Decision to keep both 'describes' relationship and 'root element' for different purposes.
* Reminder to review pull requests for three PRs for the next week.

## Discussion on 'Root Element' and 'Describes' Relationship
* Kate "DESCRIBES" relationship vs. RootElement
  * Discussion - RootElement is preference of group, but ok to keep describes for now, as long as we make it clear it is not replacing functionality.
* Sean proposed use of relationship as an immutable property of collection if it's inherent to root.
* Kate emphasized on not losing relationships as other profiles are using them.
* Decision to clarify in documentation that 'describes' relationship should not be used as root element.
* Gary committed to reviewing and updating root element description.
* Maximillian - Javascript PoC is available for experimentation.  <INSERT LINK>

## Decisions
* When serializing the physical “SpdxDocument”, any properties of the logical which can be represented in the native serialization format (e.g. @context prefixes in JSON-LD in place of the namespaceMap) will be used      and the remaining properties would be serialized within the “XCollection” types.   see: PR ???
* Tentative (pending William, Serialize, ... if no blockers in PRS by next Monday, they will be merged) - we will go with SPDXDocument and move forward.
* Keep DESCRIBES relationship and keep rootElements property - we will update the description of both to make it clear the rootElement is to be used for describing the "starting point" for Element Collections
* The term 'materialization' was used as a placeholder name for the class.
* The team decided to use native serialization when serializing the physical STDX documents.
* The team agreed that there would only be one X-collection within the serialized file.
* Every file must have a single root element, although there can be multiple root elements within the document.
* The external map would be retained as the proposal to replace it had not been vetted for all use cases.
* The team should perform tasks parallel to the next release and if the current design is not working, they would change it in the next release candidate for the SPDX3.
* The X-collection represents the logical aspects of serialization.
* The group came to a tentative decision of going with the term 'SPDX document'.
* The group decided to keep both the 'describes' relationship and the 'root element' for different purposes.

## Action Items
* all to review above PRS
* Review and update rootElement description.
* Jeff to sync up with Alexios and William for document generation.
* Dick to take responsibility of reviewing pull requests for Xcollections serialization.
* Gary to follow up with Jeff regarding disagreement on logical plain LTX collection form.

## Prior Serialization Notes from email

On Tuesday’s tech call,     summarize where we are at in the serialization meetings:   
We agreed that we need      to separate the physical “SpdxDocument” form the logical “SpdxDocument”      as it relates to SPDX 2.3  
We agreed that we will      have a class in the model to represent the logical form of the      “SpdxDocument” – name TBD – using the name “XCollection” as a placeholder      (sometimes referred to as SerializableCollection)  
We decided that when      serializing the physical “SpdxDocument”, any properties of the logical      which can be represented in the native serialization format (e.g.      @context prefixes in JSON-LD in place of the namespaceMap) will be used      and the remaining properties would be serialized within the “XCollection”      type     
There would be one and       only one of the “XCollection” type in the serialized file – this solves       the “where to we start” issue for RDF and JSON-LD   
There was not a 100%       consensus on this decision    
There was significant      discussion on the external map and a decision was made to leave the      structure of the external map largely in place for RC2 but have the      “externalDocument” refer an artifact rather than an arbitrary URI and      introduce a relationship type which would relate the SPDX document      artifact to the “XCollection”     
This was not a 100%       consensus   
There was concern       re-opening the external map discussion which took considerable time       several months ago when we were working on the model   
We agreed there was       nothing fundamentally broken with the external map, however, the       alternative could provide increased efficiencies in certain, arguably       common, scenarios   
Since the external map       is optional, we could introduce alternative serialization approaches in       the future without breaking changes    
Decide on the name for     “XCollection” – we’ll discuss this on Tuesday’s call 
Review 3 pull requests     that implement the above decisions:   
PR to document how we  serialize data which may be implemented in the native serialization      format: https://github.com/spdx/spdx-3-model/pull/509        
PR to update the      External Map to use Artifact and relationships to the “XCollection”: https://github.com/spdx/spdx-3-model/pull/542        
PR to document the      “XCollection”: https://github.com/spdx/spdx-3-model/pull/490  
Note: they all need to      be updated with the agreed upon name  
Test the efficiency of     real world uses of SPDX 2.3 External Document References with the external     map to see if there is significant issues in practice   
We will ask on      Tuesday’s call for any volunteers who have used the external document      reference to help with the analysis  
Gary will analyze the      SPDX Maven Plugin for impact  
If we find significant      issues in practice, we will revisit the external map  
Note: I followed up      with the maintainers of Tern (Ivana, Rose, and Nisha) and they      unfortunately do not use the external document references but have      offered to help in any analysis 

## Next SPDX Tech Team Meeting 2023-11-07
