# SPDX Serialization Focus Group Meeting 2023-08-31

## Attendees
* Armin Tanzer
* Sean Barnum
* Gary O’Neall
* David Kemp
* Maximilian Huber
* Jeff Schutt

## Agenda
* Continuation of the namespace discussion

## Notes
* Sean is starting to write a namespace concept paper* 
* Progress held up by lack of clarity or implementation difficulty experienced by several developers
* Reviewed Sean's use cases from https://github.com/spdx/spdx-3-model/commit/5cb4f99702bd531af709d7b8fbcccdcc74167535 
  * General agreement on the use cases with some caveat on the last use case which use useful but not as high a priority
* Reviewed Max's proposal: https://github.com/spdx/spdx-3-model/issues/489
  * Discussion on understanding the proposal
  * Sean raised concern that it doesn't fully support the use cases
    * Use cases involving an intermediate consumer/supplier doesn't pass along the original namespace hints - e.g. aggregating multiple serializations then trying to deserialization
    * Doesn't provide a mechanism for a producer to provide a more general namespace hint indepentent of serialization
* Use case actor definitions
  * Producer - the producer of an SPDX set of data
  * Consumer - the receiver of the SPDX document
  * Consumer/Producer - an actor that recieves SPDX data then produces subsequent SPDX data based on the consumed data
* Next steps:
    * Sean will complete a pull request for his proposal
    * Gary will ask Max to create a pull request with his proposal
    * We'll compare the 2 proposal against analytical critera and decide
