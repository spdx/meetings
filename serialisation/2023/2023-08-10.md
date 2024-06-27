# SPDX Serialization Focus Group Meeting 2023-08-10

## Attendees
* Gary O'Neall
* Sean Barnum
* Nisha Kumar
* David Kemp
* Jeff Schutt
* Ivana Atanasova
* Rose Judge
## Agenda
- Blank nodes
- Other serialization formats

## Minutes

### Blank nodes
- Sean: plan is to add a new file called "blank_nodes.md" to the serialization folder
- Sean: if we were going to use blank nodes, we have to follow only one skolemization mechanism
- (working through github permissions to submit the new file on a new branch)
- Gary: maybe just comment on the PR
- Sean: this is just a description of how to use the blank nodes
- Nisha: example of a JSON-LD document with blank nodes?
- David: Armin's examples are in the playground repo.
- There is a context section. You can add that to JSON to make it into JSON-LD

### Other serialization format
- We can start with simple JSON to see whether a format is still needed even though JSON and JSON-LD are syntactically the same.
- David: nice to have the examples in the playground.
- Follow up in next week's meeting

### Open topics
- David: Armin's conversion example doesn't quite catch the different creationInfos
- Gary: why would creationInfo be different? David: the payload was created at one time and the annotation was created at another time.
- Nisha: example is one playload combined with another payload like containerizing an appliation - container payload is created at one time and application created at another time.
- Jeff: issue 365 https://github.com/spdx/spdx-3-model/issues/365 i.e. granular use of profiles. For example, some elements are created under a security profile while another element is created with the software profile.
- Gary: disagree with what is written in a spec. Created a PR https://github.com/spdx/spdx-3-model/pull/447 restricting to conformance points not namespaces.
- Jeff: disagree with changing what is already defined
- Gary: we could have different profile properties. whether a property or class is in the namespace of the profile, it can be determined from the namespace
- Jeff: for the vulnerability class it is a subclass of element. In JSON serialization, does the user see this?
- Gary: for jsonld there is an @type which can help detect. In 2.3 there is an array for every type of class.
- Sean: the actual instance of this object is intended to conform to a list of profiles. Sees value in separate list for each one.
- David: type needs to be in JSON in order to know the concrete type
- Sean: in JSON-LD @type is required. Propose giving each object a type.
- Jeff: if the creationInfo has the profiles, does this mean that every element conforms to each of the profiles?
- David & Sean: separate definitionProfile and complianceProfile?
- Sean: feels it's more complicated as there are two different namespaces.

## Next meeting
- David's JSON and tag-value proposal 
