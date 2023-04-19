**Linux Foundation Collab Summit - SPDX face-to-face**

**Thursday, April 5, 2012**

## Different headers for the same license issue

How to capture in License List where the same license text has different
"meanings' indicated by different headers. Key examples: MPL v2.0
(Exhibit A or Exhibit A & B); L/GPL licenses ("or later" or "only").
Complete agreement that this information needs to be captured. Question
is how to capture/implement?

  - A)PROPOSAL 1: leave 'as is' on license list now which is that these
    scenarios are captured as a different "line item" (with distinct
    license name and identifier) for each header scenario that can
    change the meaning of the license (e.g. GPL-2.0; GPL-2.0+)
      - i)Pros:
          - a)Fedora and Fossology already uses similar short names as
            we have now (i.e. GPLv2 or GPLv2+)
          - b)Predictable and specifically identified, which is
            intrinsic to goal of license list
      - ii)Cons:
          - a)Won't match other lists
      - iii)Other considerations:
          - a)if we stay with this route, propose that short identifier
            says "only" in it?
              - (1)But then, what about when you aren't sure - which
                short identifier do you use? Default to "or later?" Is
                more intuitive to use "GPL-2.0" plain?
  - B)PROPOSAL 2: license list is just the licenses themselves. Headers
    or alternative exhibits are captured on a separate list that then
    modifies the license list.
      - i)e.g. On the master license list, GPL v2 would be just that
        GPL-2.0 (without indicating "or later" or "only"), then the
        separate list would have the headers variations of the "or
        later" text present or removed. The short identifier could then
        be modified by a sub-set of identifier or identifier extension,
        such as "GPL-2.0" + "or later" or "GPL-v2.0" + "only" - likewise
        for MPL and its exhibits. Presumably, each scenario would have
        it's own extension modifier
          - a)potential problems - more to keep track of and more
            complicated. Is the net result all the different than
            Proposal 1?

**DISCUSSION**

  - ''vigorous discussion around pros and cons of \#1 and \#2 ''
  - *variation proposed that combined both proposals*
  - ''major problem/drawback with proposal \#2 and any variation thereof
    is potential for explosion of scenarios where modifiers could be
    used in non-conformant way causing ambiguity or confusion which goes
    against goal of license list ''
  - *advantage of current scenario - it's simple (even if lengthy) and
    has rigidity needed; but some clarification needed*

**DECISION**

leave as is = separate "line items" for GPL v2 only and GPL v2 or later

**TO-DOs**

  - add in Notes field for all GNU licenses that short identifier
    "GPL-2.0" = GPL v2 only and vice versa
      - (Jilayne to do for next version of license list)
  - add other MPL 2.0 scenarios for Exhibit B (see Luis email and
    meeting minutes)
      - (Jilayne to do for next version of license list)
  - need to come up with list of all licenses that fall into this
    category (same license text appearing more than once on license
    list) and determine the "default" if SPDX file creator only files
    license with no delineating header or other information
      - (Jilayne or someone else? to come up with list and then discuss
        on one of next legal calls)

**OTHER RELATED DISCUSSION**

  - C)GPL exceptions
  - i)how to display license text? Should it be the entire GPL license +
    exception; or just the header and exception; or just match on the
    exception text?
  - *a)Did not discuss*
  - ii)How does this interplay with proposals above? If \#1, then as is
    on list, but still need to answer above questions, if \#2, then
    could treat exceptions as part of modifier/extension list?
  - *a)Also leave as is in terms of separate line items*
  - *b)acknowledgement that SPDX license list does not have all
    exceptions and will need to add more (research needed on this to
    identify holes)*
  - ''c)could we come up with a system of separate license modifiers
    that could be added on modularly to a "GPL-2.0"? ''
  - D)Standard headers for licenses
  - ''i)Currently this field only shows up on license list spreadsheet,
    but not on spdx.org license pages; need to add this field including
    ability to indicate there isn't a standard header, as is the case
    for most licenses ''
      - ''a) ''(Jilayne and Gary to begin working on)
  - ''ii)need to review license list, to make sure standard headers are
    correct; remove or indicate "replaceable" text; check if any are
    missing ''
      - a)(Karen C. and Bill to start this task)

[Minutes](Category:Legal "wikilink")
[Category:Minutes](Category:Minutes "wikilink")
