## Attendees

  - Jilayne Lovejoy, OpenLogic
  - Peter Williams, OpenLogic
  - Kate Stewart, Canonical
  - Bill Schineller, Black Duck
  - Daniel German, Univerity of Victoria
  - Jason Buttara, Cisco
  - Paul Madick, HP
  - Kirstin Newcomer, Black Duck
  - Jack Manbeck, TI
  - Michael Herzog, NexB
  - Philippe Ombredanne, NexB
  - ?? did I miss someone ??

## Guideline 1. Verbatim Text

  - "curly brackets" not "squiggly brackets"
  - in BSD-2-Clause .txt file - change to curly brackets for copyright
    year/owner (not angled brackets)

<!-- end list -->

  - suggestion to have multiple levels of matching
      - first level - verbatim, byte for byte and
      - second level - "normalized" with some words equivalent;
      - third level - matching with normalized plus variable sections
  - would this require a new field in spec to indicate what kind of
    match?
      - not going to happen for 1.1, but for 2.0? is this as simple as
        return status indication or would we need to revise "License in
        File" tag/field in spec
      - put in license comments (for 1.1 version); make it optional
        information
      - add to guidelines suggestions on level of matching

<!-- end list -->

  - want to have original text of license that was matched, before it
    was matched - capture that text as well, provides a check, i.e. the
    extracted license text from file
      - talked about how this would play out with existing fields; would
        need some use cases around this
      - should we focus on guidelines today, come back to this idea of
        extracted license text for 2.0

<!-- end list -->

  - license name and copyright notice - do we need to match on these?
    (already have rule on copyright notices, add rule for license name?)
    and if so, would we want to strip this info out of the license .txt
    files
      - probably don't want to strip out this info from .txt files b/c
        want them to appear in the wild, but can indicate the guidelines
        with the curly brackets by adding this to the license name,
        copyright notice
      - for Apache 1.1 - ignore the bottom paragraph for matching
        purposes, i.e. if it's missing, it is still a match
      - by indicating this with the curly brackets - then this avoids
        tool maker from having to make any interpretation on where to
        start/end ignore
          - put curly brackets in every .txt file around the copyright
            notice line
          - put curly brackets in every .txt file around the license
            name
          - by doing this, we have moved (back) from guidelines to
            rules?

<!-- end list -->

  - since guidelines now - still have some reference to "rules" and
    inconsistent wording with "should" "must" and "needs - should be
    "guideline" and "should" for consistency purposes

PROCESS going forward:

1.  no way to get this all done for v1.1 of spec - so update guidelines
    with items discussed today as well as incorporating "easier"
    comments on license list matching guideline wiki page
2.  distribute/notify legal list when revised page is ready so people
    can **review and comment as needed before legal call next Wed, 6/27
    - to complete (first draft, anyway) of guidelines at that
    point\!\!**
3.  project of going through all licneses to add curly brackets around
    relevant other text to be started post v1.1 - need to communicate
    via guidelines or otherwise that this is not completed yet and is a
    work in progress
    1.  will need a process for this - perhaps a first pass by one
        person who documents issues and protocols and then second pass
        by a variety of people (Philippe offered to help with this :)
    2.  will be easier to do for new licenses added to list going
        forward, but need to remember to add to license adding protocol
        process as well
    3.  once first pass of licenses done, makes sense to then go back to
        idea of "type" of match (three levels) idea at that point

[Minutes](Category:Legal "wikilink")
[Category:Minutes](Category:Minutes "wikilink")
