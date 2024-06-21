# (Hybrid) FedID CG / WG kick-off meeting - 20 June 2024

  - Moderators: Heather Flanagan, Wendy Seltzer

  - Scribes:

# Agenda

  - Administrivia
    
      - Scribe volunteer(s)?
    
      - Reminders:
        
          - [<u>Community Group
            Membership</u>](https://www.w3.org/community/fed-id/)
        
          - Updated [<u>W3C Code of
            Conduct</u>](https://www.w3.org/policies/code-of-conduct/)
    
      - Onsite Logistics (bathrooms, fire exits, etc)
    
      - Ground Rules for a Hybrid Meeting

  - [<u>Agenda
    Slides</u>](https://docs.google.com/presentation/d/1uuh6WeV1sRySQpX7uPTInz6Vlu2IPdFMn5Zk4ThG3EU/edit#slide=id.g2ddab934d8b_0_0)
    
      - 09:30 - 10:00 - Introductions (all)
    
      - 10:00 - 10:20 - The W3C Standardization Process (Wendy)
    
      - 10:20 - 10:40 - CG -\> WG Process for FedID (Heather)
    
      - 10:40 - 11:00 - Coffee Break & New Scribe
    
      - 11:00 - 11:30 - [<u>Revised Charter
        Review</u>](https://w3c.github.io/charter-drafts/2024/wg-fedid.html)
        and
        [<u>Privacy</u>](https://github.com/w3c/charter-drafts/issues/531)
    
      - 11:30 - 12:30: FedCM spec evolution
        
          - First Public Working Draft
        
          - Additional Spec Editor(s)
        
          - [<u>Harm & Threat Modeling at the W3C
            </u>](https://docs.google.com/presentation/d/1ZqN-qAjeCp13WmTyyfXQJTMS-9JVidy82UAVzyrzqDg/edit#slide=id.g2c5acd11802_0_15)(Simone)
        
          - Preparing for Horizontal Reviews (accessibility,
            internationalization, privacy, and security, TAG)
    
      - 12:30 - 14:00 - Lunch
    
      - 14:00 - New Scribe
    
      - 14:00 - 15:30 - Status of FedCM
        
          - Demos
        
          - Review of Success Criteria
        
          - Blocking Issues
    
      - 15:30 - 15:45 - Coffee Break & New Scribe
    
      - 15:45 - 16:30 - Open Discussion
    
      - 16:30 - 17:00 - Next Steps

# Notes

\[[<u>intro
slides</u>](https://docs.google.com/presentation/d/1uuh6WeV1sRySQpX7uPTInz6Vlu2IPdFMn5Zk4ThG3EU/edit#slide=id.p)\]

\[Heather\]

  - Reminder that we're agreeing to abide by the W3C's updated code of
    conduct

  - Using the Slack channel \#federation

\[Wendy\]

  - We are in a hybrid meeting. Feel free to unmute and say something
    if there are technical difficulties

  - We'll try to stick to the schedule to respect time zones

## Introductions (all)

\[Pam\] new to the WG. Work for Microsoft. Run the Identity Standards
team.

\[Arthur Coleman\] ID Privacy: AdTech, run
[<u>www.theprivacysandbox.com</u>](http://www.theprivacysandbox.com).
Done a lot of work with federated identity over the years.

\[Wendy\] Tucows, one of the chairs of the Federated Identity WG

\[Heather\] Co-chair of both the WG and CG

\[Tim\] Okta, Co-chair of the CG

\[Aaron\] Okta, been prototyping some of the FedCM work

\[Sam\] Google, working on FedCM

\[Chris Wilson\] Google Chrome - Web Standards Tech Lead

\[Christian B\] Web Platform team at Google Chrome

\[Kaan I\] Technical PM for FedCM at Google

\[Simone\] W3C staff, security lead

\[Philippe\] W3C staff:

\[Ben V\] Mozilla

\[Steffi\] DAASI International, using FedCM for SLO in Shibboleth IdP

\[Tom Clancy\] MITRE

\[Filip Skokan\] Okta, have some prototypes of FedCM

\[Bas\] Dutch R\&E federation, looking at FedCM

\[Judith Bush\] repping REFEDS

\[Phil Smart\] UK access management federation and developer on
Shibboleth

\[Michael Knowles\] Chrome Engineering manager for identity and payments

\[Alan Buxey\] Works for MyUnidays , service provider relying on R\&E
federation (SAML currently)

\[Matthew Miller\] Cisco, interested in Digital Credentials API

\[Nicolas\] FedCM spec editor from Google Chrome

\[Elf Pavlik\] Solid WG at W3C

\[Brian Campbell\] Ping Identity

\[David Waite\] Ping Identity

Late: \[Rick Byers\] Google Chrome, Web Platform Area Tech Lead

## Administrivia

\[Heather\]

  - Since this is the kickoff meeting, today will be a bit of
    administrivia. FedCM is the working group's focus at this time.

  - How W3C is planning to handle threat modeling, W3C process, then
    break for lunch

## The W3C Standardization Process (Wendy)

\[[<u>slide
5</u>](https://docs.google.com/presentation/d/1uuh6WeV1sRySQpX7uPTInz6Vlu2IPdFMn5Zk4ThG3EU/edit#slide=id.g212012f5346_11_0)\]

\[Wendy\]

  - Some have worked with the W3C process before, others may not have.
    Welcome to all\!

  - First public working draft, one or more candidate recs, and
    endpoint of either Candidate Rec or living standard (create
    periodic CR snapshots to trigger review)

  - Beginning of the progression: first task is to publish the first
    public working draft (FPWD)
    
      - Taking the output from incubation and deciding it is good
        enough to put on the recommendation track
    
      - WDs do not necessarily represent consensus of a WG or
        endorsement by the W3C
    
      - Generally a low bar for moving things forward
    
      - Triggers the first of the [<u>royalty free patent
        policy</u>](https://www.w3.org/Consortium/Patent/)

  - Hopeful we can get consensus here or soon after that on getting to
    FPWD
    
      - People can implement and expect that this will be the shape of
        the APIs, the set of features they can build their apps
        against

  - CR doc that satisfies the requirements of the WG that produced it

  - Horizontal review from security and privacy, accessibility,
    internationalization. Does the spec satisfy the needs of the
    broader community?

  - Throughout, looking to gather implementer experience. CR phase is
    formally the time calling for implementation.

  - Keep going through CR drafts, then periodically in the living
    standards process, asked to mint CR snapshots. Important to secure
    patent commitments.

  - Unlike FPWD, CR phase does require consensus of the WG. Consensus
    does not mean there aren't compromises. In IETF speak, might mean
    there are people in rough consensus, but made strong efforts to
    address concerns. Discussion on issues that get to the bottom of
    understanding the concerns they are raising. Good faith
    discussion, attempts to reach resolution, sometimes required to
    bring things to a vote.

  - Questions?

\[Sam\]

  - Can you give us a sense of what are some of the hardest parts, any
    words of guidance, in your experience? How long do you expect
    things to take, etc?

\[Wendy\]

  - We have a good starting point from incubation. That means we're
    not starting from a blank page. We've been seeing this work
    progress in the open for a while now, with lots of community
    input. Sometimes in other WGs, the surprises and difficult parts
    are that the thing that you thought was finished, may not have had
    feedback from new folks.

  - Someone coming in with fresh eyes, may have fresh ideas that will
    help advance the work. Be respectful in pointing people to past
    conversations. Ask whether they have new input or new
    considerations that would reopen the discussion.

\[Nicolas\]

  - Wondering what is the best way to handle features that are in
    incubation vs the generally agreed upon in living standards mode.
    PRs vs a better way?

\[Wendy\]

  - Some folks here have been working in groups that have both CG and
    WG

\[Heather\]

  - What I'd like to see published, a draft document that says what
    we're testing and here's where things stand with what is being
    tested. landing page that we can point to

\[Rick Byers\]

  - Context: we've got a bunch of active users of FedCM in Chrome.
    Will have to react to their feedback as they continue using it.

  - Not an option for CG to block and not react to the feedback, but
    want to work in coordination with WG

  - Better to work on branch than monkey patchh

  - Open to whatever working mode works for other participants

\[Wendy\]

  - The spec becomes the work of the working group. Change control
    rests with the WG. If there are things that an implementer needs
    to do for their implementation, free to work off a branch of the
    spec, but the spec will be under change control of the WG.

  - May have started as a Google feature, but very much now a W3C WG
    product and everyone should feel ownership of the work

\[Rick\]

  - Always a balance to implement and innovate and also do it in a way
    with open governance on the spec

\[Sam\]

  - Nicolas, I think you were asking a logistical question. How do
    things in the CG shift to the WG. Lot's of things in the CG that
    are still in flight and haven't been merged. Maybe we could have
    forks of the repo, where the fork has the baseline of the spec,
    and changes are made to the fork, and the fork could move to the
    WG.

\[Wendy\]

  - Github has lots of facilities for managing branches, tracking
    changes, etc. Developing versions that incorporate a selection of
    PRs. Open to input on good practices from other experiences and
    groups.

\[Wendy\]

  - Extra slide on chartering. Might be some more discussion around
    that, but can defer to later

\[Heather\]

  - Time to talk about CG / WG working together

## CG -\> WG Process for FedID (Heather)

\[[<u>slides 6, 7,
8</u>](https://docs.google.com/presentation/d/1uuh6WeV1sRySQpX7uPTInz6Vlu2IPdFMn5Zk4ThG3EU/edit#slide=id.g212012f5346_11_58)\]

\[[<u>CG-\>WG
Process</u>](https://docs.google.com/document/d/1gxf3HG-W8py4WzW4Pv761oVy_LHmx6CpzmHZajdDKRE/edit#heading=h.j7n44aj1zrxc)\]

\[Heather\]

  - Process leaves a lot of wiggle room. How do you actually do it?
    Incubate new ideas, get into spec, manage conversations?

  - Lots of flexibility (good and bad), there's no one true way for
    how a CG informs a WG

  - In some cases when a CG forms, its to incubate an idea and see if
    there's enough behind it to form a WG, then sometimes the CG goes
    away

  - That's not what we're going to do. Our model will give CG input
    into the process. E.g. have an idea that could improve FedCM and
    want to get input on it.

  - Designed a 6 stage process. Inspired by TC39.

  - Easier for many to join a CG than a WG, don't want to lose out on
    those ideas

  - Stage starts at 0, people submit new ideas in new repo
    
      - Got an idea, got a proposal. Start with issues or text.
    
      - Gives CG time to think about and then shift to stage 1

  - Stage 1, CG dives into it and discuss whether it meets multiple
    needs or only one need
    
      - To this point, we're under CG rules.
    
      - If CG thinks it has legs (might still need work), then it
        moves to stage 2

  - Stage 2, WG has heard feedback from the CG, and brought it into
    the WG.
    
      - Still draft, still subject to change, could still be rejected

  - Stage 3, solidly in the WG
    
      - Proposal is approved and vetted
    
      - No changes to proposal unless implementation feedback leads to
        changes
    
      - Testing and feedback

  - Stage 4, we think this is pretty much ready
    
      - Encourage additional implementers to start testing
    
      - Further implementation input

  - Stage 5, WG consensus that this should go into the spec

  - Will use Github in many interesting ways, will rely on experience
    of others

\[Ben V\]

  - Looking for clarification on which of these stages corresponds to
    CR publication.

\[Heather\]

  - CR is stage 4.

\[Elf P\]

  - Which stage would there be testings for RPs?

\[Heather\]

  - WG covers web platform tests

\[Tim\]

  - Not something W3C typically does

\[Tim\]

  - E.g., OIDF could offer this for OAuth / OIDC binding for FedCM

\[Arthur\]

  - Privacy Sandbox incorporates multiple specs across many repos. One
    of the things that came up in PA. There are features in GH that
    allow voting.

  - Couple of people have written AIs to help other people get answers

  - Question: where do code samples happen in this process?

\[Heather\]

  - People bring in implementations and prototypes. E.g., Phil has
    brought in some Phil Smart. Aaron has done for IndieAuth.

  - People who don't have time to participate in the standards
    process, still feel like they need to know what the implementation
    details look like. Not part of the W3C WG process; done
    separately.

\[David Waite\]

  - Are there other CGs/WGs with this arrangement in the W3C?

\[Heather\]

  - Chris Wilson has been guiding us.

\[Chris Wilson\]

  - Immersive Web CG/WG has followed roughly this approach (but hasn't
    written it down as a process).

  - Looked at TC39 and WebAssembly; they use this system pretty
    closely.

  - CSS WG has something similar, also not written down.

  - As new WGs get created, tried to pair them with an incubation
    venue, but have them explicitly called out

\[Pam\]

  - Granularity of what constitutes a proposal. Assume it is not a
    document? How big or small?

\[Heather\]

  - Stage 0, it's a GH issue. Doesn't have to be a complete explainer.

\[Sam\]

  - Self-contained problem statement.

\[Heather\]

  - Could set up an issue template.

\[Bas\]

  - Question about the distinction between CG and WG: is it expected
    that WG members also participate in the CG?

\[Heather\]

  - Think it would be sensible because they are better informed of
    background discussions, etc. But not required.

\[Tim\]

  - Probably depends on what role you plan to take. Like, if it's your
    issue, and you plan to write the spec text, then maybe you should
    just write an explainer.

\[Sam\]

  - What is the diff between stage 3 and 4, in terms of what gets
    produced?

\[Heather\]

  - Text is mostly done because you've done the implementation.

\[Chris Wilson\]

  - 3 is where the proposal is approved in principle, iterating on the
    bits of the API. When you get to 4, unless you have
    incompatibilities, it's moving.

\[Sam\]

  - Still believe that CR is stage 4?

\[Chris\]

  - CR is probably late in stage 4. CR also means different things
    depending on how long it has been in CR. Can go to Rec quickly. By
    the time you get to REC, you're done.

  - Some of the feature level complete / ready to be included, is
    earlier. You're essentially done by the end of stage 4.

\[David Waite\]

  - Do all normative changes go through this process? If not, where
    does the existing body of text coming from the CG start in this
    process?

  - If, for instance, someone in the WG wanted to propose changes to
    the login status API, is this document coming in as stage 3 from
    the CG, or would it be instead happening without CG involvement?

\[Heather\]

  - There will be a point where it moves to the WG.

\[Tim\]

  - There will be stuff in the WG that will not be discussed in the
    CG.

\[David Waite\]

  - If changes in the WG affect the CG proposal, there could be
    concern from CG members.

\[Jeffrey Yasskin\]

  - In the W3C, there's a "wide review" stage that happens before CR,
    so stage 3 could be the point where it gets sent to wide review,
    changes are addressed, then moves to stage 4 for CR?

\[Heather\]

  - Could be a bridge point between 3 and 4.

\[Philippe\]

  - The WG process prefers to have earlier reviews than later reviews.
    Encourages WGs to ask for early review. Especially things that are
    I8N related.

\[Philippe\]

  - There's a WG repo with proposals, should that be in CG?

\[Heather\]

  - Some stuff is going to move.

\[Pam\]

  - Physically pick it up and move?

\<resuming from break\>

## [<u>Revised Charter Review</u>](https://w3c.github.io/charter-drafts/2024/wg-fedid.html) and [<u>Privacy</u>](https://github.com/w3c/charter-drafts/issues/531)

\[[<u>w3c/strategy\#450</u>](https://github.com/w3c/strategy/issues/450)\]

\[Heather\]

  - 11:00 PDT — Welcome back

  - As many know, when the WG was formed there was a suggestion (not
    blocking) — Federated Identity WG might be a good home for
    activity in the WICG WG when it was ready. This wasn’t universally
    well received, so that suggestion was tabled until after the
    initial charter process.

  - [<u>A github
    issue</u>](https://github.com/w3c/strategy/issues/450) has
    outlined/discussed concerns/mitigations, coordinated by Simone.

\[Simone\]

  - \<showing issue\>

  - [<u>https://github.com/w3c/strategy/issues/450</u>](https://github.com/w3c/strategy/issues/450)

  - Goal was to work on not only federation but also decentralized
    creds

  - Received feedback from Ping; it was positive

  - Was accepted by the previous version of the charter

  - Don’t know yet what the consensus is; feedback was just out last
    week

  - Still waiting for the official answer but next week will move on
    this

\[Philippe\]

  - 2 days ago, talked to the co-chair; said it was fine to move
    forward with the charter

<!-- end list -->

  - One PR is the only thing pending

\[Simone\]

  - Fingers crossed that next week this goes out

\[Heather\]

  - If it goes out, how long is the voting process? \[answer: 28
    days\]

\[Philippe\]

  - The deadline for the review is 28 days. If there is an objection,
    that could expand to 3 months.

\[Heather\]

  - If we manage to avoid formal objections, is it possible to be
    re-chartered by July's end? \[confirmed by Philippe/Simone\]

  - If not chartered by end of July, there could be a conversation at
    TPAC

\[Philippe\]

  - If not chartered by the beginning of September, a request to start
    a council will be made before TPAC. We can still work on finding
    common ground at TPAC.

\[Simone\]

  - Will try to collect concerns and discuss the charter, so that
    would be a place to discuss

\[Heather\]

  - Tim, if the WG re-charter is approved over the summer, what would
    happen to the WICG calls, how would they be absorbed?

\[Tim\]

  - Transition would likely be post-TPAC, because some WICG sessions
    are already planned.

\[Rick\]

  - Is this full absorption?

  - Will play by ear.

\[Heather\]

  - We can update the charter, so that WICG can have a forum

  - Marko from Apple has concerns re: parallel CG/WG interactions

\[Rick\]

  - Hopeful that the digital credentials work will be “one and done”.
    FedCM is more product/feature rich, so great if all the work can
    be done in WG, but need to make sure input is always welcome and
    collected

\[Tim\]

  - Notes that everyone can always leave a comment so everyone should
    have opportunity

\[Heather\] - no questions on charter? (confirmed)

## FedCM spec evolution

### First Public Working Draft

### Additional Spec Editor(s)

\[Heather\]

  - Next - talking about FedCM not digital credentials

  - Homework assignment is a first public working draft. We have a
    snapshot of the spec as it is now/today that we might use as the
    first public draft. Doesn’t mean we have consensus on features but
    puts a stake in the ground. It lets us see how the work is moving.
    Concerns?

\[Wendy\]

  - for the W3C process, publication would require a WG “decision”;
    there will be an online/mailing list call for consensus.
    Discussion here is welcome, but the decision will still go out to
    the mailing list for further input before there is a final
    decision.

\[Pamela\]

  - Can we have a high-level discussion of what that doc does?

\[Heather\]

  - We have a status of FedCM after lunch, a review of the charter
    would that work? \[Pam agrees\]

\[Ben\]

  - Which of the states best corresponds to what we are talking about?

\[heather\]

  - Stage 2.

\[Ben\]

  - Request that we note inline where we might not have changes yet
    (Heather agrees)

\[Heather\] - today our FedCM spec has one editor (Nicolas)

  - Looking for 2 separate implementers/independent 3rd parties to
    hold the spec (rather than just one)

  - Not expecting answer today, but if anyone is interested in
    stepping up as editor, contact the group/Heather/Nicolas

\[Ben\]

  - I have been putting the strongest flag about things not in
    consensus in the CG — as written it would be tough for me to be an
    editor. Others may have similar issues

\[heather\]

  - there is the idealistic version of being an editor, and the
    reality of the work. Those are different things. Within the group,
    your name on the spec means you are committed to working to make
    the text better, indicating ownership and support

\[Wendy\]

  - Since some folks are newer to W3C, we can define the role of
    editor: help shepherd the document, facilitate changes, help call
    for discussion among the group when there is a deeper feature
    change, and assess when the group has reached consensus to know
    when to accept a PR. You do not have to be sole decision maker,
    but help the chairs assess consensus, flag divisive issues, and
    help to progress the documents. This should be open to people with
    a range of interests who can dive in to understand the spec

\[Rick\]

  - If the ideal can’t happen, I’ve seen cases where consumers of the
    spec can be very effective as editors, e.g., in this case, IDPs

\[Pavlik\]

  - Ben has a good understanding and has provided great feedback —
    maybe there could be editors for different versions of the draft
    to show who is responsible for which iteration of the doc

\[Sam\]

  - Question, once you have a good working draft, next step is getting
    consensus for a candidate recommendation

\[Wendy\]

  - You could have multiple working drafts

\[Sam\]

  - At what stage does the requirement come in for two
    implementations? It would be useful for Ben to know what it would
    take to get from stage 2 to 3 or 4 that are on your mind as we
    transition. Not needed now, but important to make progress

\[Ben\]

  - There are issues about AuthZ, IDP support, can give a list of
    issue that represent those concerns

\[Sam\]

  - A bunch of things you are seeing as concerns are being incubated
    as state 1 proposals, e.g., multiple IDP support, AuthZ. Since
    those things are getting incubated and as they mature, as the
    proposals work into the WG that’s when some of Ben’s concerns
    would be resolved. Is there anything that isn’t being actively
    worked on or that you feel is blocked?

\[Ben\]

  - I have been vocal, think everything is covered

\[Heather\]

  - Another thing impacting work is desire for explicit harm and
    threat models Sam has authored one for digital credentials work —
    Simone can you talk about this

### [<u>Harm & Threat Modeling at the W3C </u>](https://docs.google.com/presentation/d/1ZqN-qAjeCp13WmTyyfXQJTMS-9JVidy82UAVzyrzqDg/edit#slide=id.g2c5acd11802_0_15)(Simone)

\[Simone\]

  - Just to understand some misconceptions — if you like we can do a
    session
    [<u>https://docs.google.com/presentation/d/1ZqN-qAjeCp13WmTyyfXQJTMS-9JVidy82UAVzyrzqDg/edit\#slide=id.g2e6b6b03404\_0\_0</u>](https://docs.google.com/presentation/d/1ZqN-qAjeCp13WmTyyfXQJTMS-9JVidy82UAVzyrzqDg/edit#slide=id.g2e6b6b03404_0_0)

  - I like to add something physical

  - This is a repeatable process — subject to brainstorming

  - \<describes threat modeling\>

  - Example of threat modeling

  - Threat modeling is a mindset; Shostack’s 4 question framework can
    be used:
    
      - 1\. What are we working on?
    
      - 2\. What can go wrong?
    
      - 3\. What are we going to do about it?
    
      - 4\. Did we do a good job?

\[Pam\]

  - In \#1, when you say the output is a “schema”, is that
    specifically a data schema?

\[Simone\]

  - The answer is contextual; for example, see the slides on “which
    model is better”.

  - Discusses which model is better.

\[Pam\]

  - I think our definitions of schema are different, will infer from
    context

\[Simone\]

  - Have created a template and can book a session to “play”

\[Heather\]

  - This is the definition of a threat/harm model that W3C wants to
    see

  - We have a threat model for decentralized credentials, but is the
    goal to create one for FedCM along the same lines?

\[Simone\]

  - Yes,

\[Sam\]

  - Would love to work to create threat models, there are also the
    security/privacy considerations in the spec. Is what you are
    trying to produce different from what is in the spec today?

  - Commented in the zoom meeting to give link to privacy section:
    [<u>https://fedidcg.github.io/FedCM/\#privacy</u>](https://fedidcg.github.io/FedCM/#privacy)

\[Simone\]

  - The threat document is for a different audience, and also may
    survive over time and across specifications. (Simone will add
    additional points in case the scribe didn’t capture it correctly)

\[Pam\]

  - If the harm/threat model is separate per spec, it could be common
    between, for example, Fed CM and Decentralized.

\[Sam\]

  - Guessing they could start separate and be reused; each of those
    approaches may deserve their own point of view.

\[Rick\]

  - Part of the reason why there is excitement about digital creds is
    that the threat model is specifically different. Starting with a
    different threat model is a feature not a bug.

\[Simone\]

  - The threat model is something that could be updated on a different
    cadence as new threats arise; analyzing the cryptographic pieces
    takes longer. If there is an important change, updating the spec
    should be a different process. The important thing is that it
    exists somewhere.

  - Added an example of a separate threat model doc:
    [<u>https://datatracker.ietf.org/doc/html/rfc6819</u>](https://datatracker.ietf.org/doc/html/rfc6819)

\[Brian Campbell, via slack\]

  - Is broader/general harm through further encouraging centralization
    and monoculture something that's in scope for this threat model?

\[Sam\]

  - Seems like a reasonable observation

\[Simone\]

  - This is a philosophical discussion, have seen some folks keeping
    security/privacy separate

### Preparing for Horizontal Reviews (accessibility, internationalization, privacy, and security, TAG)

\[Heather\]

  - In addition to internal stakeholders, we have a number of external
    organizations (such as OIDF) that want to perform horizontal
    reviews. Are there any guidelines for interacting with those orgs?

\[Philippe\]

  - See [<u>document
    review</u>](https://www.w3.org/Guide/documentreview/). In terms of
    how early should horizontal reviews, suggest that we should do it
    early rather than late. Do not wait; for privacy/security, go
    earlier; internationalization, earlier; accessibility, later.

\[Judith\]

  - Would use of pop-ups qualify as an accessibility issue (and
    therefore late)? Ben indicated this was an accessibility issue.

\[Phillipe\]

  - When in doubt, do it early.

\[Ben\]

  - Yes that is the kind of thing to do early, because it forces a
    pop-up on mobile, and that could be an issue.

\[Heather\]

  - This covers initial steps of how to move the WG along. We have put
    out a call for editor volunteers, discussed threat/harm, and
    talked about timing for horizontal reviews. Questions, comments?

  - For the afternoon: coming back at 2pm PT (in 1 hour 45 minutes)
    and will talk about spec details, etc. Eventually, we will get to
    open discussion. If we haven’t covered something you care about,
    now is the time to have that conversation. Thanks to scribes. See
    you after lunch.

\[Wendy\]

  - The [<u>Federated Identity Slack
    channel</u>](https://w3ccommunity.slack.com/#federation) is a
    great way to continue the conversation\!

  - 
Meeting reconvened at 14:00 PDT

### Status of FedCM

Demo from Sam -

FedCM 101 presentation from OSW:
[<u>https://blog.timcappalli.me/p/preso-osw24-fedcm101/</u>](https://blog.timcappalli.me/p/preso-osw24-fedcm101/)

  - \[Sam\] demos booking.com with Sign-in with google

  - \[Pam\] That’s a demo of when the browser and the IdP coincide,
    right?

  - \[Sam\] Yes, that’s the case in this demo. The FedCM API works
    with other IdPs, so any would do, except that it has to be one.

  - \[Tim\]
    [<u>https://blog.timcappalli.me/p/preso-osw24-fedcm101/</u>](https://blog.timcappalli.me/p/preso-osw24-fedcm101/)
    — Here is how the Multiple IdP UX looks, which would allow more
    than one IdP to be used at the same time.

  - \[Baz\] How does the trust model work?

  - \[Aaron\] each “type” has its own

  - \[Aaron\] demos webmention.io

  - \[Arthur\] What level of control does the website have?

  - \[Sam\] the RP has some choices in terms of widget vs modal vs url
    pills

  - \[Pam\]

  - \[Filip\] demoing the button flow + continuation.

  - \[Filip\] here is a user that is logged out, clear session, user
    clicks a button. User is taken to login. They confirm they want to
    continue. The IdentityCredential already includes your id token,
    the same format that you’d get in a query. The RP can pipe this
    into their system.

  - \[Filip\] Now, for the consent part, prompt=consent, but then, I
    get my consent screen in the continuation API. also works in any
    response type. As a result of this, I get the authorization
    endpoint. I can also ask for a code; that’s ok, too. This is using
    the parameters API, the button mode as well as the continuation
    api. If I’m already logged in and asked for more scopes, I’m
    prompted just like the regular authorization prompt.

  - \[Pam\] …in that you are getting an authorization code back.

  - \[Filip\] Yes, in a world where you are moving to implement FedCM,
    it is good that the website can degrade gracefully in the absence
    of it.

### Open Discussion

  - Discussing Ben’s list:
    [<u>https://github.com/fedidcg/FedCM/labels/mozilla</u>](https://github.com/fedidcg/FedCM/labels/mozilla)

  - \[Sam\] As a start: proposing
    [<u>\#442</u>](https://github.com/fedidcg/FedCM/issues/442) as a
    less-controversial starting issue. There is at least one proposal
    at origin trail “button mode”

  - \[Judith\]: the origin trail for button mode is an IDP you already
    have a relationship with
    ([<u>https://developers.google.com/privacy-sandbox/blog/fedcm-chrome-125-updates</u>](https://developers.google.com/privacy-sandbox/blog/fedcm-chrome-125-updates))

  - \[Sam\] if the RP specifies the IDP (typical flow for social login
    such as “sign in with google”), there is a proposal for
    introduction of button mode that checks whether the user is logged
    out and, if so, takes the user back to the IDP to login.

  - \[Phil\] this is where the IDP is returning “no account”

  - \[Aaron\] there is both no relationship and no account at the IDP

  - \[Phil\] does that mean the RP is calling all the IDPs

  - \[Sam\] the origin trial now only calls 1 IDP

  - \[Nicolas\] - the flow in the issue is widget mode. It would be
    quite challenging to have the user be logged in and then become
    successful. Asking if the button mode origin trial is sufficient
    to address Ben's concern, or does he also want a solution for
    widget mode?

  - \[Heather\] Let's ask that question on the issue

  - \[Pam\] Right now what's in the OT is a "login with google or
    login with facebook". Are we concerned about a nascar scenario
    with buttons then? Would that be the workaround that people would
    have to take?

  - \[Aaron\] Yes, saying the same thing as "the problem is not solved
    in multiple IDP"

  - \[Sam\] Correct. We don't know how to do this when the IDP hasn't
    been selected, but if you select the IDP like today via button
    flows, then it works.

  - \[Pam\] This is about IDP discovery, but just for some flows
    right?

  - \[Aaron\] Today, RPs have a nascar screen with some list of IDPs
    they choose. Now that can be enabled with FedCM and they can be
    successful. That's what's enabled with button mode. Same nascar
    screen but is solved by FedCM instead of redirects. Whether we can
    solve the nascar flag problem is a separate one — the multiple IDP
    issue that's being discussed.

  - \[Pam\] What about the identifier-first flow that happens for IDP
    initiation — starting with the IDP.

  - \[Aaron\] Then you're logged into the IDP, and you don't have a
    problem

  - \[Pam\] OK, I'll file a separate issue for this — not sure it's
    addressed

  - \[DW\] seems like there could be a circumstance (like the original
    account chooser) where the the user maintained state that FedCM is
    now asking the browser to take over and had that flexibility, but
    now we don’t have that — we could start with a more simplistic
    nascar representation and then

  - \[Judith\] If I have an active session with one multiple IDP, it
    isn’t clear it falls down and says… it seems that there is a
    presumption that my active IDP is the one I always want to choose,
    rather than letting me prefer to use an alternate IDP

  - \[heather\] Do we have that documented?

  - \[Nicolas\] suggest adding to the Multiple IDP issue and I can
    move it later if needed

  - \[Sam\] - is it ok to only use in button mode

  - \[Nicolas\] - I think so, because we can fall back on Nascar, so
    the question is how prominent should we show all of this within
    button mode (this will be an issue in widget mode too). Part of
    the origin trial, we decided to focus on widget, but only under
    experimentation — focusing on widget first, but if there is demand
    for multi-IDP button mode, I think it is something reasonable to
    expect from the browser. The question is, when? It might take some
    time.

  - \[Aaron\] I think it should be a separate issue, Judith’s question
    was specifically about button mode.

  - \[Sam\] That is what we are doing; today, there is no login button
    that takes you to a browser API. The Nascar flow has usernames,
    too.

  - \[Pam\] not always

  - \[Aaron\] often there is a login button that takes you to a login
    page that displays all the options.

  - \[Nicolas\] we are not trying to get rid of login pages,

  - \[Sam\] you wouldn’t be able to get rid of all the

  - \[Aaron\] are you trying to solve specific situations where
    regular logins can co-exist, or are you replacing redirect logins,
    breaking them in the process?

  - \[Phil\] when we say “login to an IDP” we say two things — 1)
    login state at the IDP or 2) state at the API, do we mean both?

  - \[Sam\] could be both

  - \[Phil\] it could be one or the other as well; you could have API
    state but no session at IDP, or the other way around

  - \[Sam\] need clarification, but for button flows with single IDPs,
    we have an answer for [<u>issue
    \#442</u>](https://github.com/fedidcg/FedCM/issues/442)

  - \[Sam\] next least controversial is
    [<u>\#555</u>](https://github.com/fedidcg/FedCM/issues/555). There
    is UX experimentation that needs needs to happen but the API shape
    is well understood
    
      - When an authz server requires extra prompts, it opens the
        pop-up window to ask

  - \[Heather\] Why is this in the less contentious bucket?

  - \[Sam\] With those 3, we have a reasonable proposal for how to
    move forward. [<u>Issue
    \#441</u>](https://github.com/fedidcg/FedCM/issues/441) has to do
    with Filip’s point earlier, that right now you have to expose
    FedCM endpoints to implement, whereas if we could reuse existing
    oauth/oidc endpoints, everything would be easier.
    \#[<u>441</u>](https://github.com/fedidcg/FedCM/issues/441) is
    exploring ways to do that.

  - \[Judith\] Do you have a SAML version as well as an OAuth version
    of FedCM?

  - \[Sam\] I wish Ben was here, but as soon as you go through one
    permission prompt, you unblock the gates, allowing native protocol
    negotiation

  - \[Sam\] Right now the last assertion is the identity assertion
    endpoint but we would even remove that

  - \[Filip\] So once we get past that first consent, cookies could
    work and they could talk as much as they want?

  - \[Sam\] - Yes

  - \[Filip\] So this would reduce the IDP scope to the discovery and
    accounts endpoint?

  - \[Sam\] The lightweight endpoint proposal is to remove even the
    account endpoint

  - Ben’s proposal here:
    [<u>https://github.com/fedidcg/CrossSiteCookieAccessCredential</u>](https://github.com/fedidcg/CrossSiteCookieAccessCredential)

  - \[Sam\] This isn’t controversial in that we all agree on the goal
    we just haven’t thought enough about the solutions and
    alternatives

  - [<u>\#407</u>](https://github.com/fedidcg/FedCM/issues/407)
    Authz/relation to ability to specify scopes

  - \[Heather\] not sure why Ben has considered this as controversial

  - [<u>\#317</u>](https://github.com/fedidcg/FedCM/issues/317) -
    Concerns about email in Accounts List
    
      - \[Sam\] If I understand the problem correctly, not all IDPs
        want to share the user’s email or have it at all. Need to find
        a way to make that optional
    
      - \[Aaron\] The point of email in there is just for
        identification of the account; adding a username as another
        option is fine because it is just another identifying string;
        don’t need to overload it with types for processing
    
      - \[Sam\] There is one small complication but we can discuss it
        separately. It is not controversial to work on, but it is not
        a problem.
    
      - \[DW\] This has been a struggle in Webauthn as well because
        the fields are not extensible due to hardware limitations, but
        the field representations have differed by form factor. Going
        to a displayname and a passkey provider equivalent
    
      - \[Sam\] The suggestion was “human readable identifier”
    
      - \[DW\] The goal is to distinguish
    
      - \[Sam\] In the specific case of your work account, everything
        is the same
    
      - \[DW\] If you ask for a passkey for a personal and business
        account, everything looks the same. At that point, you need an
        account differentiator at the IDP.
    
      - \[Pam\] Is this in the threat model? If an attacker can get
        the wrong entry into the list?
    
      - \[Heather\] Should be in the list as we draft it, even if only
        initially before we winnow
    
      - \[Heather\] wheeee\!

## Next Steps

  - \[Heather\] we have exhaustion and next steps — talked about a
    draft of what the CG+WG process looks like, one outcome is a
    github-centric side meeting open to anyone but goal is to inform
    what people should put where

  - If you haven’t read the revised charter, please do that. We want
    to avoid formal objections if possible, so if you haven’t talked
    to your AC rep, that is also a good idea

  - Link to the draft charter here:
    [<u>https://w3c.github.io/charter-drafts/2024/wg-fedid.html</u>](https://w3c.github.io/charter-drafts/2024/wg-fedid.html)

  - Link to W3C strategy repository here (any time W3C is thinking
    about a thing, this is where the discussion takes place):
    [<u>https://github.com/w3c/strategy/issues/450</u>](https://github.com/w3c/strategy/issues/450)

  - Both things are going to the mailing list sooner or later
    
      - Request for editors
    
      - Note about what happens next

  - Will be a separate stream of work around the threat model. As we
    find things that touch on accessibility, UX, etc., Wendy and
    Heather as chairs will reach out horizontally

  - We want multiple implementations but also want all stakeholders to
    communicate what their needs are

  - 137 open issues, currently — need to sort to find what is urgent
    and could prevent future blocks

  - Keeping with CG call schedule for incubations, WG calls likely to
    be once/month, will get something out to the group, it may be a
    split call to accommodate different TZs

  - \[Wendy\] Thanks to hosts for their generous support and for those
    who scribed

  - \[Heather\] Thanks to those on the other side of the ocean who
    stayed awake\!

  - \[Wendy\] Hoping this is giving a sense of who is in the room, and
    how we can operate in good faith to get problems solved. If you
    have a question, please reach out directly, to chairs, in Github….
    How many issues can we resolve simply with increased comms, and
    how many are questions that just don’t have solutions? Excited and
    encouraged to see the energy and hoping to have good issue triage
    by TPAC

  - \[Heather\] Thank you to those who brought up issues around
    recognizing the history that brought us here, thank you for being
    brave, otherwise we could be driving people away and nobody wants
    that

  - \[Wendy\] Thanks to Simone who travelled all the way to be here
    and then had to isolate\!\!

Meeting closed — see you all soon\!

  - 
*\[WS notes, I think we’re note taking in two different places in the
doc. Can’t reconcile them in real-time, but there are some notes from
this session at the bottom of the doc.\]*

*Action items\!*

  - *Side meeting on github logistics, will be announced and open,
    goal is to document expectations*

  - *Revised charter is out, please review it before it goes to AC
    vote; support it with your AC rep.*

  - *Call for consensus on FPWD*

  - *Call for spec editors*

  - *Workstream on harm and threat model, work with Simone*

  - *Issue triage*

  - *CG calls for incubation; WG scheduling to list.*

\[Success Criteria\]

  - \[Heather\] What does “done” look like?

  - \[Heather\] (presents slides)

  - \[Heather\] 2 independent implementations.

  - \[Bas\] OIDC vs SAML

  - \[Heather\] from a protocol perspective, SAML doesn’t need this
    because SAML doesn’t need cookies. There are certainly SAML
    adjacent things, like IdP discovery, and there are cases where we
    haven’t figured out how some of these work.

  - \[Bas\] Isn’t FedCM supposed to help through 3PC across domains?

  - \[Judith\] I know that I had communication with the Chrome team
    about some of the ways around third party cookies, SameSite=None,
    and those are what’s involved in cross-site, and how Chrome is
    considering navigational tracking.

  - \[Bas\] a SAML flow isn’t so distinct from a tracking site, so
    that’s hard.

  - \[Judith\] given the flexibility of the “attributes” that can be
    sent on the request, we could use it as the redirect protocol.

  - \[Filip\] the SAML binding is similar to the OIDC binding, not
    sure if it is a direct goal to reuse the endpoints. You’d have to
    transform the request to connect to your current deployment.

  - \[Brian\] OpenID and OAuth also don't use cookies that SAML
    doesn’t. The motivation here, there is something that is
    mismatched. There seems to be this ongoing mismatch of the
    motivations and needs, I recognize that it is kinda of moving
    forward. The larger question at this point, is it possible to
    channel the SAML request/response through this API?

  - \[Tim\] it could be as simple as a SAML binding to have a “SAML
    request and a SAML response”. Someone needs to write it and find a
    home, probably just a couple of pages.

  - \[Judith\] the signature would have to be included in that
    parameter too.

  - \[Tim\] yeah, that just needs to be written down. That’s just on
    someone to do and find a home for it.

  - \[Phil\] channeling Scott, adoption would be hard, you’d need to
    get standardized, etc. I just think it would take a long time to
    do that.

  - \[Bas\] convince the SAML IdPs to adopt things

  - \[Heather\] shows the table where it shows the expected breakages

  - \[Brian\] I wanted to highlight the amount of “nos” in that table

  - \[Heather\]

  - \[Sam\]- The mental model from the start was to take partitioning
    as a start, not the end goal. The idea was to enable things that
    couldn’t be done otherwise. We have always taken the position that
    the loss of 3PC is a nuisance, not a curse.

  - There are things that can only be done if you have a browser in
    the middle, that cannot be done with the neutral third party

  - From the start it was a two-phase approach — preservation and
    extinction — we should build the browser API so that when things
    break, the browser can preserve what things break

  - So with 3PC, we should have an answer for that

  - That is a better approach than if we have to handle bounce-track
    mitigation all at once

  - You can focus on extinctions individually more easily than you
    could do otherwise

  - Gives us more flexibility

  - 
\[Phil\] - --- (fill in please)

\[Same\] - When it comes to preservation — assume you are referring to
the ---- discussion

\[Phil - Not just that, but replying to the preservation. It is not
preservation when every entity in the current flow has to change
something. But from RPs perspective, they don’t have to change much but
they will still have to….

\[Tim\] - Preservation of an end state — different than how we get
there. In this, the RP has to do the least, the browser does the most. I
agree that preservation may not be the ideal word.

\[Sam\] - Want to minimize the amount of change — it can’t be zero — so
it is a minimization search. Trying to preserve what we can with as
little change as possible. Been talking to the browser vendors about
this.

\[Phil\] Didn’t mean to get hung up on a single word. It sounded like
preserving state is very restrictive. We are not talking about having
the user change something when things go wrong.

\[Sam\] - We are trying to keep users unaware of the change as much as
we can — so maybe preservation is not the best word. We want to keep the
system to keep running to the best of our ability with as minimal change
as possible. No one has ever found a solution that allows us to not have
tracking on the web *and* have zero changes

\[Tim\] I agree that third party cookies aren't the perfect framing.

\[Brian\] there was at least where the framing was a lot of preservation
in the absence of third party cookies. We should recognize that there
are some people who aren’t as excited about the browser stepping into
the identity journey. And stepping back into the history of the group,
it is not clear to me that things outside of third party cookies have
always been a goal.

Blocking issues

\[heather\] where do we have issues?

\[Sam\]
[<u>https://github.com/fedidcg/FedCM/labels/mozilla</u>](https://github.com/fedidcg/FedCM/labels/mozilla)

\[Heather\] multiple idps

\[Heather\] working from that issue list

\[Aaron\] What’s the definition of blocking?

\[Heather\] in order to get multiple implementations

\[Aaron\] Are we talking about browser implementations? Or are we
talking about RP and IdP implementation?

\[Wendy\] what’s blocking the group’s consensus?

\[Judith\] I filed 618, came up at the end of the last meeting of the
community group, Sam started talking about navigational tracking
mitigations, that’s one of the pieces right now … but that’s chained
authentication flows that are very common … the FedCM UX doesn’t handle
that well … I do want to make sure as we go forward that this issue is
kept prominent in the FedCM work, so that it will be clear it is great
for the third party cookies piece, but until this issue is resolved,
being able to support navigational-tracking is a bigger issue.

\[Sam\] We can choose to take collective risk: do we want to address
navigational tracking mitigations? My intuition is that we should be ok
with the unknown, for now, as we don’t yet know how bounce-tracking
mitigations will materialize. Suggest we take the risk of waiting, as we
don’t yet know enough to know what to do about it?

\[Judith\] I support that anything we put in a spec shouldn’t look like
bounce-tracking. Also, we should recognize that FedCM as-is doesn’t mean
we aren’t using any identifying primitives. Still leaves the privacy
community concern. Navigational mitigation makes the SAML folks look at
this.

\[Pam\]

\[Sam\] Bounce-tracking and chained authentication are
indistinguishable, as far as the browser is concerned. We’d want to
distinguish them, but no one knows how. My proposal to this group is to
not try to solve that distinction problem right now, because we don’t
know what the browser intervention on bounce-tracking is.

\[Pam\] We can’t break chained authentication.

\[Tim\] Regardless of what mitigations will be, we can make the
statement that we can’t rely on query parameters. We don’t have to wait
to understand the intricacies of enforcement

\[Sam\] We can have a task force on bounce-tracking. Concerned that we
should not spend a long time on a hypothetical problem.

\[Judith\] Not saying we have to have FedCM solve chained authn flows.
But if it doesn’t, it can’t be used as an alternative to flows that look
like bounce tracking.

\[Brian\] I’m hearing some seeming contradictions in how we describe our
scope.

\[Sam\] I believe FedCM will be a meaningful part of the solution, but
we don’t know enough about the problem to say it’s a complete solution.
Necessary but not sufficient.

\[Brian\] We shouldn’t over-claim what FedCM solves, if there are
multiple layers.

\[Tim\] Similar to FedCM being a signal for user consent, user
visibility

\[Phil\] preparing a demo for July 10 showing nested flows.

\[Heather\] July 10 webinar — see registration link (free) in the slack.

\[Phil\] Asked whether IDP registration is a signal for exclusion from
bounce-tracking mitigation.

\[Nicolas\] I think the answer is “no” because the user saying that “I
want to use this idp” should not imply “I’m allowing this idp to know
everywhere I've visited”. From a privacy perspective, I don't think that
would pass Chrome’s reviewers' bar.

\[Phil\] Yeah, I can see your argument.

\[Pam\] Origin trial has login w/ Google, Login w/ Facebook. Are we
concerned about the NASCAR effect?

\[Aaron\] That’s the multiple IDP problem

\[Pam\] This is IDP discovery for only some flows?

\[Aaron\] Today, RPs do have a NASCAR screen with some IDPs they choose.
They can display the same screen through FedCM (button mode). Whether we
want to solve the NASCAR problem by pulling the flag out of the page
into the browser is a separate problem, multiple IDP issue.

\[Pam\] Starting at the IDP

\[Aaron\] Then you’re logged in, so you don’t have the problem.

# Queue 

  - \<please use Zoom hand-raise\>

# Attendees (sign yourself in)

  - Philippe Le Hegaret (W3C)

  - [<u>Heather Flanagan</u>](mailto:hlf@sphericalcowconsulting.com)

  - Wendy Seltzer

  - Alan Buxey (MyUNiDAYS Ltd)

  - Chris Wilson (Google Chrome)

  - Judith Bush (REFEDS)

<!-- end list -->

  - Christian Biesinger (Google Chrome)

  - Michael Knowles (Google Chrome)

  - Steffi Dobretzberger (DAASI International)

  - Simone Onofri (W3C)

  - Tom Clancy (MITRE)

  - Bas Zoetekouw (SURF)

  - Phil Smart (Jisc/Shibboleth)

  - Tim Cappalli (Okta)

  - Aaron Parecki (Okta)

  - Filip Skokan (Okta)

  - Sam Goto (Google Chrome)

  - Nicolás Peña Moreno (Google Chrome)

  - Zachary Tan (Google Chrome)

  - Chris Fredrickson (Google Chrome)

  - Rick Byers (Google Chrome)

  - Ben VanderSloot (Mozilla)

  - Jeffrey Yasskin (Google Chrome)

  - [<u>Ted Thibodeau</u>](https://github.com/TallTed/) (he/him)
    ([<u>OpenLink Software</u>](https://www.openlinksw.com/))

  - Brian Campbell (Ping Identity)

  - David Waite (Ping Identity)

  - [<u>elf Pavlik</u>](https://elf-pavlik.hackers4peace.net)
    (independent, Solid CG)

  - Matthew Miller (Cisco)

  - Pamela Dingle (Microsoft)

  - Arthur Coleman (IDPrivacy)
