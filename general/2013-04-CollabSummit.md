**COLLABORATION SUMMIT SUMMARY**

For those of you who didn’t make it to the Collaboration Summit, below
is a summary of the different components of the event. It was pretty
inspiring in a number of ways…for me, it felt like the rubber is finally
meeting the road seeing real tools—our own, from academia, and
commercial—putting out real live SPDX docs. The every positive KarenC
summed it up as “The discussions have much more of a feeling that this
has to happen – the only questions are around how.” And I agree.

All the team leads did an outstanding job organizing our ever expanding
involvement in Linux event. (Now we even get our own track.) Gary, MarkG
and Adam were also key in pulling this off.

## Tech Team Working Session

In this session we went through the current model proposal for 2.0, and
discussed options that would simplify the model, and still meet the use
cases we're targeting. We were also able to start off the relationship
and element usage enumerations. Full details can be found at:
[Technical\_Team/Minutes/2013-04-16](Technical_Team/Minutes/2013-04-16 "wikilink").

## Legal Team Working Session

The SPDX Legal Team met at the LF Collab Summit to hash out the
remaining bits of the License Matching guidelines. Namely whether SPDX
should provide "guidelines only" in regards to what is to be considered
substantive text of a license for matching purposes or whether SPDX
should go further and provide some kind of actual markup or examples in
regards to text than can be ignored or considered "replaceable" for
matching purposes. And, if the latter, to what extent and in what format
to provide such markup or examples. The legal team, with good
representation from various tool makers and tech team members, decided
that markup was needed to avoid potential differences in interpretation
by tool makers. It was decided to use simple markup that could be
illustrated within a .txt file, as that is the (mostly) preferred
download format for the licenses. The exact details of the markup are
being worked out and the Legal Team (with help from anyone else in the
SPDX Workgroup) will manage getting the markup created for the entire
current SPDX License List.

## Open SPDX Discussion

Mark Gisi from Windriver and Adam Cohn from Cisco held this session on
Tuesday afternoon. It was held under Chatham House Rules which means
“When a meeting, or part thereof, is held under the Chatham House
Rule, participants are free to use the information received, but neither
the identity nor the affiliation of the speaker(s), nor that of any
other participant, may be revealed.”. Now before you say hey you just
said you weren’t supposed to mention names, these two were the chairs as
listed on the SPDX schedule.There was a lot of good discussion. One
individual talked about how they are fully integrating SPDX into what
they their company delivers and how they are shipping, and I believe the
number was, over 500 SPDX documents with each release. They also had a
website for generating SPDX documents. Others talked about how they have
started to integrate SPDX into their compliance process using it for
reviews but not yet quite shipping. The reasons seemed to vary for that
but they appeared to be more procedural than SPDX related. One
individual did raise a concern on the amount of time that it might take
to generate SPDX documents adding that it increased the cost of their
compliance it was not something they could do. A few individuals talked
about the adoption of SPDX among open source projects. There was some
discussion on how this could be done now as there are a few open source
tools that have appeared to generate SPDX documents. One individual
talked about how they would like to see SPDX become more fully
integrated into the community meaning that practices normally associated
with an open source project such as peer review and so forth were used
and considered part of the process of generating, reviewing and editing
SPDX documents.

## SPDX Morning Sessions

Mark Gisi (the man that Scott calls “the spiritual leader of SPDX
adoption”) kicked off the morning with License to Kill…You Code, a very
cogent treatise on why it’s important for copyright holders to get it
right if they want their projects to thrive. Then Gary “the Toolman”
O’Neall lead a panel on Tooling up for SPDX. He gave an over view of
group, community and commercial tools that are now compatible with SPDX.
Gary was joined by Matt Germonprez of the University of Nebraska Omaha
and Sameer Ahmed from Wind River Systems who both talked in some detail
about work their groups have done to “tool up.” Conclusion: This stuff
is real\! And to prove it…

## SPDX Bakeoff

The SPDX Bakeoff was held Wednesday afternoon. Our main objective was to
compare SPDX output from different tools in order to identify bugs and
resolve different interpretations of the specification. We had great
representation from the various tool providers, members of the SPDX
working group, and a number of other interested parties. Gary O’Neall’s
excellent spreadsheet comparison tool was used as the basis for
comparison of the various SPDX files. Per the agenda, we first stepped
through the complete Time package on a file by file basis. Following
that we dove into Busybox but only at the package level. There was a lot
good discussion and yes we did find some bugs in the tools and areas
where the specification needs to be improved. All in all it was a very
productive session and should serve to advance the adoption of SPDX. The
spreadsheet along with notes from the session are captured on in this
Google doc folder:
<https://drive.google.com/?tab=mo&authuser=0#folders/0BxKdX878M2HCTlZIbkZSMXN6SGc>
