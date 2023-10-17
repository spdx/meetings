# SPDX AI Team Minutes 2022-10-19

## Attendees
* Gopi Krishnan Rajbahadur
* Kate Stewart
* Sal Kimmich
* Chris Blask
* L Jean Blask
* Karen Bennett

## Notes
* Sal and Chris Overview
* NLP Set fully compliant with the license: https://pile.eleuther.ai/paper.pdf
* Model data 1.0: https://docs.google.com/document/d/1M-JNBtNvqxg51AjP8G5yJwzhtzv5RW-RyDxiAIDQloY/edit?usp=sharing
* CIPAM example:
"Name": "CIFAR-10",
"Original": "Alex Krizhevsky, Vinod Nair and Geoffrey Hinton",
"Location": "https://www.cs.toronto.edu/~kriz/cifar.html",
"Version": "Python version", //NO ASSERTION IS NOT AVAILABLE FOR THE FIELD
"License Completed": "NOASSERTION",//At file level
"Declared license" :"CC0-1.0", //Ask how to express non-standard licenses at the file level... Do it through the license reference
"Built/Created/collected/assembled/obtained/cured Date":"",//No affirmation required
"Release date":"2009",//Only year may be available, current format may not be suitable
"Valid until date":"",//No affirmation required
"Data collection process (include sources)": "CIFAR-10 and CIFAR-100 are labeled subsets of the 80 million tiny image dataset. They were collected by Alex Krizhevsky, Vinod Nair and Geoffrey Hinton.",
"Intended use?":"",//Nothing available--At file level
"Type":"IMAGE",
"Checksum":"c58f30108f718f92721af3b95e74349a (python version); MD5: 70270af85842c9e89bb428ec9976c926 (Matlab version); MD5: c32a1d4ab5d03f1284b67883e8d87530 (binary version)", //Multiple versions and may require support for multiple Checksum types -- Method and cehcksum can be specified and the guy needs to be checked
"Noise in data":"",
"Size":"1.63e+8",//Keep bytes
"Sensor(s)":"",
"Standards":"",
"Known biases": "May contain obscene images",
"Sensitive personal information": "Yes", //We need to define what is sensitive personal information
"Anonymization method used?":"",
"Confidential data?":"NO CLAIM",
"Dataset provider": "Alex Krizhevsky, Vinod Nair and Geoffrey Hinton",
"Errata":"",//Not sure how to use this field: SPDX annotations need to be expanded (possibly a text field for now)
"Dataset update mechanism":""
https://pile.eleuther.ai/paper.pdf 

## Discussions
* we will have to consider adding NOASSERTION to the version information
* Personal information: faces of people -- NOASSERTION is correct? Are faces sensitive personal information?
*Jean: California Civil Code: Race, sex, or biometrics should be considered sensitive personal information.
* Gopi: Cross-reference databases are where the danger occurs. Is there any sensitive personal information?
* Jean: it is presence of recognition - that is. trying to classify cats, it doesn't matter if they are faces
* Karen: Is it ISO 5388? It has many of these definitions, sensitive personal information is facial or biometric.
ACTION: I need to classify the personal sensitive data a little better and decide.
* Date: You may need to relax as timestamps are not always available. The creation date may not have been published online.
* Some of the other fields will need to be clarified, see Gopi's notes.

* Karen will be looking at Waymo data sets with us next week.
* some questions similar to Gopi.

* Karen: So many new standards...put it as email. We'll upload to git and keep adding.
* Concern about so many personalized copies: what is a standard?
* ISO and IEEE have standards for terminology and process, and it is not clear who to follow.

* L. Jean - DHS has a Tools working group
