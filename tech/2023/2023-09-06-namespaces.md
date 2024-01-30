# Call on Namespaces
## Attendees
* Bob Martin
* Gary O'Neall
* David Kemp
* Sean Barnum
* Jeff Schutt

## Minutes

What we agree on:
- A subset of the use cases (some new ones were added in PR's which haven't been discussed)
- NamespaceMap will be in the model
  - Namespaces are portions of Element ID IRI's
- The model will always use the full IRI in every element
- NamespaceMap are specific to supporting serialization (check)
- All model proposals have an "X-Collection" as an outer shell
- NamespaceMaps are only useful in collections
- NamespaceMaps can only be used on collections
- Serialized data is composed of one or more element values that may or may not be included in an ElementCollection

Definition of serialization : Persisting model data in a manner that it can be reconstituted (deserialized).  Within the context of persisting the data for the purpose of "transfering" the model data.  The transfer can be between organizations, within organization and even with the same individual or tool who/which is acting in different roles.

Impact of using NamespaceMap with serializations

Model Data -> serialized data -> Model Data
- Model data always has full IRI's - 
- Purpose of the prefix is to make the serialized data more concise
- Purpose of the NamespaceMap is to provide consistency in the prefixes used

Serialized Data -> Model -> Serialized Data
- Model data always has full IRI's
- Serialized data  may have full IRI's and/or prefixed IRI's
- The prefix to a portion of IRI is the namspace map
- Purpose of the prefix is to make the serialized data more concise
- Purpose of the NamespaceMap is to provide consistency in the prefixes used

Before serialization does the X-Collection exist?

Open questions:
 1. Prefixes can be tied to a specific serialization instance "payload"
      - supports this flow: Serialized Data -> Model Data -> Serialized Data -> Model Data? - To be discussed on the Serialization call.
      - ensures reproducibility of serialized data values previously used? 
      - X-collection represents a serialized instance
 2. Prefixes can be tied to a specific set of elements that are not (yet) serialized
 - supports this flow: Model Data -> serialized data -> Model Data
 3. Not tied to any set of elements - just part of the model <- out of scope for current SPDX release
 
 - The intent of namespaceMap are to impact the serialization but not tied to a specific form of or instance of serialization
