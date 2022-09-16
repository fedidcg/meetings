# FedID CG TPAC 2022 Day Two
-   Moderator: Heather Flanagan

-   Scribe: Cameron Boozarjomehri, Erik Anderson

Call-in details: see
[<u>https://www.w3.org/events/meetings/90dfd3a8-b42b-4981-a09f-d911e8959257</u>](https://www.w3.org/events/meetings/90dfd3a8-b42b-4981-a09f-d911e8959257)

Agenda
======

-   Administrivia / Recap / Level Setting

-   [<u>Decision Tree Diagrams</u>](https://github.com/fedidcg/use-case-library/tree/main/decision_tree_flows) - Red Question marks

-   Next Steps for FedID CG Work Items

    -   FedCM Update

Notes
=====

-   Yesterday

    -   Charter Discussion

    -   Updates on Bounce Tracking (Heather will share notes)

-   Decision Trees

    -   Heather: Advertising team loved it

    -   Tim: What do the “?” address? The question marks for RP and IdP
 are not from same org. Front Channel, user on logout is
 redirected to IdP, and will use 3rd party cookies to logout
 users of different iframes. Fragile but many enterprises use
 it. Consumer facing rarely uses federated logout. IdP just
 asserts things about you, where as enterprise side the IdP can
 also do attestation and revocation. Back Channel Logout
 requires state maintenance.

    -   Kris: Back channel is difficult because it is hard to link
 clients (in sales force use case)

    -   Tim: Many consumer services use this process of same party
 federation. Same for ESPN with Disney. 3rd party is Using
 Google to login to none Google controlled/affiliated service,
 only attesting an Id is consistent. If IdP and RP from diff
 orgs we don’t know how to ensure logout. Is this scenario out
 of scope for FedCM? Are Backchannel logout issues still a
 thing in 2022?

    -   JohnB: Frontchannel logout significantly impacted by this shift.
 Enterprise side we are getting in to scary discussion around
 enterprise policy that eliminates privacy controls or do we
 address this in a manner that is usable in a manner for end
 user to consume

    -   Erik A (MS): Implies 1st party sets exist

    -   Kris: 1 version is future state and assumes these proposals
 exist

    -   Erik: from a scoping discussion is this front channel logout
 across origins?

    -   Kris: is origins and parties

    -   JohnB: some expectation to handle this across origin nothing to
 help across parties.

    -   Heather: Is this something that needs a new API or we have a
 number of new work items from CG or do we need something new?

    -   Kris: I can say for sales force we have an interaction
 equivalent for user to enable storage access API

    -   JohnB: need it to be bi-directional grant

    -   Erik: extend storage access

    -   Martin: are we assuming FedCM is operative here, if folks have
 been said before FedCM, whether that works for Idp, if I say I
 can’t do backchannel that means all of this is broken. The
 whole point of FedCM is to link2 sites explicitly and this
 says practicality is int eh way but the system works. Don’t
 know who to notify don’t have state and cookies

    -   Kris: right now in 3rd party cookies

    -   JohnB: lots of enterprise hoping to enable FedCM

    -   Martin: assumption that RP and ID have binding to link users
 between sites

    -   Kris: FedCm can say for Sales force, we talk about use cases
 versus 1st party sets and CHIPS

    -   Martin: the alternative is storage access, that’s un workable

    -   Kris: that was our issue, we have 400 domains. If we do prompts
 to users they won’t understand all the sites (even with just 1
 prompt)

    -   JohnW: Are you suggesting users use &gt;100 sites in 1 login

    -   Kris: sales force has 9-10 different clouds with X different
 products. Might be Ecommerce, chat, etc

    -   Erik: talking about 1 user

    -   Johann: think about office and all the IdPs involved

    -   Ben: Would be nice to have fed solution solved to be reasonable,
 articulate the problems for FedCM and is this a problem for
 anyone? If this is outside scope of IDP I wanna hear

    -   Vittorio: If IDP not tracking RP we have problem, can’t do
 distributed logout, FedCM lives at app later and may change
 auth in inconvenient ways. Action change in ID , the main
 problem is so much prior work and may take a lt to stay where
 they are. Maybe special cookie just for login/logout (not for
 info or tracking) just boolean. If we do front channel logout
 allows us to just clear this 1 cookie, should not be used for
 tracking. Can infer we use this type of cookie, limited to
 different cookie

    -   Martin: Would like to see something like that, number of ways to
 exploit cookies for tracking, but can have you, as RP,
 register something with browser that can be deleted means you
 can have login state someone else can negate (but still
 enables some degree of tracking). If done in FedCM login, this
 is contextually okay because of the surrounding grant. Done
 without transparency then it’s a tracking vector. I am
 interested to see such a proposal, may need to engage some
 consent interaction.

    -   JohnW: Apple Webkit, Editor of login status API (isLoggedIn)
 light wieght way to tell where user logged in and out. Maybe a
 write only action for this type of login and get say of where
 to log you out. Can’t allow rogue IdP to log you out, proposal
 to bring that work to this group.

    -   Kris: That’s what these trees are for.

    -   JohnW: maybe user needs to provide url to logout server side and
 let browser tell the server

    -   Sam: could be something controlling that 1 bit, IDP API is
 subset of what john has in mind, extended to 3rd party APIs.
 On meta point, I think progress comes from exploring counter
 proposals. If storage access can help, lets do that. Login
 status API proposal will help make progress. Early on looked
 at things like API to start Enterprise Profiles, very
 enterprise specific, with enterprise policy can try to unlock
 some of these thing, have user for this, diff between personal
 and work use, Trigger red flag that RPs are looped in

    -   Vittorio: this is relevant to bespoke systems. Postpone logout,
 may have this discontention.

    -   Erik: should be in scope for FedCM to remember specific browser
 profile. What RP linked with IDP, sites consent to clear
 storage via iframes, do we need something more specific? Need
 to work on this with exact mechanism.

    -   James: Point out the issue of how do we know user consented to
 certain party sharing data? Linked to the [<u>thinking to
 modify FPS to enable
 this</u>](https://github.com/WICG/first-party-sets/pull/86)
 might help this group. Grateful to Martin for acknowledging
 that once a user has consented to tracking that “we can do a
 lot more”. The question is how do we get that signal.

    -   Ben: Login status API, wanted to throw out straw proposal of
 problem, what do we do if user not logged in? At some point
 need page controlled by IDP on different ways to do this. Add
 point where IdP when brought up in prompt/RP, user can consent
 to linkage of IDP and RP to IdP controlled page, and login
 status API CALL CAN BE MADE AND GO BACK TO ORIGINAL CONTEXT
 NOW LOGGED IN. Domain name is inside of chrome, but the
 interface is in page in browser (maybe in different tab), and
 fire off IdP login to close window and navigation.

    -   Peter: Not sure how this deals with logged in iFrames, seems to
 be partial/not full solution

    -   JohnW: when creating proposal, had dedicated iframe that allowed
 access to Storage Access API, allow for more login than
 logout. Things to help with that signal

    -   Tim: We need a SID or something to identify IDP, binary bit
 isn’t helpful. Lots of folks have multiple sessions in
 browser, logging out sessions in 1 go would be annoying. There
 are IDPs that need to make changes and some that don’t, need
 to decide, does this fold in to fedcm or do we need specific
 carve outs for each case? There was a point where we got
 access to storage flow, so do we converge this or decide a
 different direction?

    -   Johann: Would be great to see and end to end solution to
 understand compromises/trade offs made. Still concerned that
 we seem to have different baseline assumptions, i.e. login
 status + FedCM seems fine given mediation, as Martin
 mentioned, but then Salesforce/Kris doesn’t seem to want
 mediation. We should write this down and pay attention to
 these assumptions.

    -   Kris: I’m okay with interbrowser mediation but more important
 when done on domain. In this case these domains don’t need to
 interrupt UX.

    -   Tim: already have someone at the IDP, don’t want them to
 interrupt with popups.

    -   Kris: we have end users in the public, and then we have
 customers just going to these sites, that second group is most
 affected

    -   Johann: People interested in coming up with these and seeing
 they agree

    -   Heather: this feeds into a “what do we want to do next s a
 group” discussion. What’s it take for login status api, or
 other efforts.

    -   Sam: does edge have a solution or counter proposal to make MS
 products work on EDGE?

    -   Erik A: Frontchannel logout, what do they want, statefulness,
 server call? DOn’t think we figured that out yet but realize
 each IDP is different. May be a common primitive, if I want an
 API to mediate logout or clear storage more aggressively,
 something to help user IDP and site manage login state. Need
 to document this

    -   Tim: we only get 1 shot to do this, whomever did this retired.
 Do t=storage access for this and IDK for something else

Heather: last question was what are the next steps for this CG and our
work items. One of the things I heard in our last hour was some
additional folks on logout signals and writing down some ideas on that.
Pretty interesting, can talk about that in the next hour if we like.
Make sure we’re on the same page on things with FedCM. Some folks
assuming what FedCM does and may like some more info. If there’s any
other ideas, I’m updating the charter and would love to hear feedback on
things we explicitly need to say we’re focusing on. Were there any
thoughts during the break on logout signals that we might want to cover?

&lt;crickets&gt;

Heather: Sam– FedCM update?

Sam: Sure. This will be a bit impromptu, a few last minute slides. Feel
free to interrupt.

Sam: Useful to go over an intro of FedCM, since there seems to be a lot
of confusion. Give a sense of timeline– started 2-2.5 years ago. A bunch
of prototyping, dev trials, and recently have been running Origin Trials
which is actual developers in production with real users. Forward
looking timelines– Chrome announced phase out of 3p cookies in Q3 of
2024. That’s when 3p cookies start getting blocked. Q3 2023 is when all
of the Privacy Sandbox APIs will be available for general availability,
APIs needed to replace use cases should be available then.

Sam: to be concrete from a pixels perspective, this is an account
chooser UX. Pick accounts from IDPs. In the absence of 3p cookies, the
protocol is constructed so that the IDP doesn’t learn who the user is
until the user consents. IDP learns after the user consents; doesn’t
keep the IDP blind entirely, but prevents tracking from being done in an
unconsented way.

Sam: That’s what we implemented, it’s what’s in the spec. Our promise is
that once you have this baseline/signal that the browser can have to
know that you’re logged into a web site with an identity provider, can
lower some privacy constraints to help the user.

Sam: some numbers from origin trials (again, real users, real production
traffic) to give you a sense of where things are at. Chrome is the only
browser that exposes this, possibly Edge as well. Firefox is starting to
prototype/implement FedCM and given a favorable analysis with some good
criticism as well. Safari directionally supportive, would like feedback
from them. Good TAG feedback as well. A handful of IDPs trying the API,
some big, and more small names. A lot of handholding, can’t say a lot of
IDPs will support but learning a lot. For the few IDPs we’ve been
working with, deployed to 20+ real web sites, and about 100K users see
it. Many ways it could have gone wrong and it didn’t. Validated some
premises, generally going well. Largely as a result of the community
group, we heard a lot of feedback. Two very foundational to our work
that we want to resolve quickly– Ben found a timing attack in our
protocol where an attacker could abuse the API to track the user. Took
that to heart, don’t think we’ve completely solved it but think we’ve
done our homework. There’s a possible intersection with Login Status
API. The other feedback we saw is that the IDP account chooser makes the
wrong balance, so we’re iterating on that quickly recently.

Sam: timing attack problem is over a few hours in a session, attacking
it by considering how requests are made and correlating times.
Acknowledge it and mitigating it is hard.

Sam: architectural changes– the timing attack is the pull model, we pull
the accounts from the IDP and, in doing so, we reveal who the cookie is
to the IDP and have a timing attack. Started that way since it was easy;
the architectural shift worth noting is that it’s a push model. Instead
of pulling accounts on demand, we push it to the browser. IDP pushes to
the browser to avoid the timing attack. That’s hard, but think we found
a sweet spot between deployment challenges and privacy benefits. Calling
it the IdP sign-in status API. Narrower than login status API, keeping
track of if the user is logged into the IDP or not. Look at HTTP heards
and JS APIs, exact API TBD. That addresses a subset of the timing
attack. Strict subset of the push model.

Sam: that implies some UX to be constructed to sign into the IDP which
is something we’re considering. Once you have an IDP sign-in status API…
don’t know what that looks like. If the browser knows you’re logged into
a web site, there’s a lot of places we think we could convey that to the
user. &lt;shows a mock where there’s a profile icon near the address
bar&gt; Identity more of a first-class citizen.

Sam: also having multiple IDPs in the account chooser. Trying to make
things backward-compatible as much as we can, making deployment easier.
Our API right now gets an array of providers, making it so it supports a
list. &lt;shows mocks with multiple IDP account chooser&gt;; multiple
IDPs show up, causes a massive UX challenge but we think it’s a solvable
challenge. Your Facebook account, Google account, etc. could be used to
sign in. We think there’s something special about returning users. If
the browser already knows you have an RP account with an IDP it might
show first. Playing with it still.

Sam: volume– some quieter UI based on if the user has shown an intent to
sign in. A modal dialog might make sense, but an omnibox UX may make
sense. We have a whole deck with explorations of possible browser UX. To
connect it back to John’s intuition that sign-in status is a first-class
citizen connects with some mocks that show the user’s login state in the
browser UX could be interesting.

Sam: To address a comment to Vittorio yesterday– back in 2020 we said we
think there are 3 solutions: classes of solutions and focused on
mediation, but knew it wasn’t as expressive as it needs to be especially
in enterprise scenarios. Ossification is a concern we have as well. Now
that mediation is better understood, and it’s also not perfect for
privacy, not applicable for every use case across the board. May have
some scenarios where the IDP doesn’t learn anything. Both permission and
delegation oriented approaches worth exploring.

Tim: a concern with the mock with the UX in the omnibox, may preference
an IDP. If Google sign-in first to the browser, may prefer those. Google
on a Google device, Apple on Apple, Microsoft on Edge, etc. Don’t love
the NASCAR problem but it’s a level playing field.

Sam: it’s a concern we share and need to come up with better answers for
this.

Manu: decentralized identity spec chair. High amount of overlap with
verifiable credentials. Picking between wallets that contain credentials
like citizen card, movie royalty card, etc. W3C also incubating mobile
document API, payment request and handler APIs, four disconnected sets
of work happening at W3C that all deal with choosing of some kind.
Choosing an IDP, choosing a wallet, choosing a payment instrument. Not
this group’s problem, but it’s a general problem at the W3C that we have
these account selection mechanisms happening in different places, coming
up with bespoke solutions. Need to come up with some amount of
coordination. Appreciate you reaching out, Sam, to do that coordination.
In scope for the charter to coordinate?

Sam: I don’t think it’s in-scope for this group, but it’s something you
should expect to see from the Chrome team.

Manu: interest in verifiable credentials group on coordinating on this.

Sam: orthogonal to this, but another area is with fast keys and other
auth mechanisms. Multiple IDP choosers, multiple document type choosers,
certificates, etc. No disagreement that there’s a lot of intersection
with other stuff.

Tim: where things diverge a bit is that a VC and DID is not ?. Could be
a superset API. &lt;lots of TLAs&gt; Should work together, but not pull
it all into one.

Vittorio: zooming out a lot and looking at the charter of the group and
what FedCM does– if you look at a list of all of the values, use cases,
etc. we identified. FedCM seems to be before that. Especially with
mediation model, it’s not as much that the browser is aware of identity
happening. It’s a nuclear option where it says “now I’m going to do
identity.” Somewhat an alternative to what we do in the identity space.
The verifiable credential thing highlights you’re trying to do the same
thing and will step on each others’ toes. Chrome’s account selector and
how it would work without cookies, but in the past couple of years I’ve
observed it’s just hard to go to all of these people that have been
doing identity all this time and innovating and saying “here’s an
alternative where we do it on your behalf.” I’m having a hard time
reconciling the FedCM scenario and how it aligns with the charter of
keeping federated identity working. When we talk about logged in APIs, I
can see opportunity for integration. But FedCM does things that identity
is already doing. I fully recognize your right to do whatever you want
for your product, and it’s a valid scenario, but I don’t know that it
can be used to substitute it for everything else we’re doing.
Front-channel logout, sure, you’re not constrained to cookies– instead
of keeping what you had working you instead provided something new. I’m
hoping we can do something a bit more gradual. I hope all of that made
sense.

Ben: I thought you had a lot of good points. I agree that perhaps
there’s some degree from a purely privacy perspective I don’t care much
about if the user picks the particular account in that dropdown, I care
about that the user is informed about the parties linking. The
permission delegation structure as a relative newcomer to the group I
didn’t have context but fits into the proposal I threw out before the
break. I think there’s some utility in looking at that framework.

Kris: my feedback is that we look at FedCM right now as an account
picker. The account picker doesn’t always make sense. As we go through
the flow, we look at (a) which browsers support this– Chrome vs.
everything else we might need to support Storage Access API, but if we
need to use Storage Access API anyway to get access to cookies, it makes
sense for us to just never hit FedCM if it doesn’t cover the full scope.
A big part of our feedback is if it does one very specific use case it
needs to have value in that use case, otherwise we’ll likely just go
with other mechanisms/tools.

Johann: I still want to understand if that’s same-party federation or
federated.

Kris: we have many scenarios. Same-party federation where users log into
our portals, e.g. Salesforce portals. End-users coming to us. Also have
our products being put into employee portals, e.g. microsoft.com hosting
a Salesforce component. Also have solutions where we’re the IDP. We have
a whole spectrum.

Johann: for this group, is it something that has to be solved under the
umbrella of FedCM?

Kris: doesn’t have to be under FedCM. We don’t care about the solution;
we care about if our IDP needs to go to FedCM but need to switch to
Storage Access API to continue, don’t want to have two prompts. More of
a cohesive solution than what the solution is, if that makes sense.

Johann: is there enough utility to FedCM for the 90% of use cases that
aren’t Salesforce?

Kris: I look at FedCM as the account picker, that’s the use case.

Tim: wasn’t a problem statement in scope initially. We’ve been a bit
frustrated about pitching to folks internally is we weren’t setting out
to fix the account picker.

Heather: while I don’t want to over-index on one company’s issue no
matter how massively complicated it is, we did talk about if we could do
a decision tree from Salesforce’s perspective.

Kris: I did do that for tomorrow.

Johann: my question is generally just about how much should be in scope
for this group.

Kris: so far we’ve been including same-party federation. The terminology
gets difficult, what’s SSO, what’s the definition.

Johann: what do we want from a user perspective, how can we do that with
the privacy guarantees we want to uphold, and then go into
implementation details.

Ben: to address one thing from Mozilla’s perspective– same-party
federation is cross-party federation. If you’re crossing the origin or
site boundary, if you truly do control these things you can CNAME or
what have you and those are fine.

Sam: re: comments from Kris and Tim– need to get into what problem set
we’re trying to solve, I feel like front-channel logout is one of the
use cases we enumerated and said we should solve. We did find a
solution, but didn’t find one that is very great. The idea that in the
spec we go, “because you have looked at the account chooser/the user
interacted with it, they get to do front-channel logout.” You can
disagree it’s a good solution, not easy to deploy for Salesforce (which
is very valid criticism), but it’s a bit indirect. In decision trees,
front-channel logout would be helped by FedCM which is one of the things
that would break when 3p cookies go away.

Kris: the problem for us isn’t that we’re against going through FedCM
for the account picker. It’s FedCM account picker, then immediately
after getting a Storage Access API prompt, etc.; it’s the daisy chain of
steps in user interaction. We would be fine/more than happy if FedCM
could also trigger Storage Access API so we could do other things. Don’t
necessarily want to ties FedCM to Storage Access API. Let’s figure out
these points in the decision trees and then Salesforce will look at it
and go, “this proposal covers 90%, so we’ll likely implement that and
then do one-off types of things.” But FedCM isn’t covering 90% today.

Tim: the account picker is a net positive for account picker. NY Times
needs an identity and then we go. The hard line where the account picker
is the least of our concerns because we already have one.

Kaustubha: I hear Ben saying the user understands it as a separate
party, but I’m struggling as a browser engineer thinking about login use
cases, I think about them as partitioned by something that has global
identity. Maybe totally wrong as a mental model, but it’s how I map to
browser mechanisms like partitioned cookies where there’s some notion of
partitioning. Identity as a service provider like Okta. The identity for
every Okta customer is different. Identity on Okta customer 1 and Okta
customer 2 are different. Federated identity providers like Google sign
in or Twitter sign in, has the notion of partitioned identity that it’s
loaning to another site. FedCM provides those privacy and user
experience controls. Same party single sign-on is different because
there’s some notion of partitioning, but only to the domains within the
same first-party. Take sony and PlayStation– different than Google and
YouTube. It just so happens that google also has Google sign-in.
Thinking about the BBC or Sony and Playstation where they provide
identity to other owned-and-operated domains. Still looking for identity
scoped to that set of domains and don’t expect it to be shared with
another 3p site. Mozilla says it wants to treat same-party the same as
cross-party.

Ben: I think the ergonomics of same-party login/SSO vs. an identity
provider in the way Google and Facebook offer, there are ergonomic
differences. You identity ways to allow an identity provider in this
context to say “don’t allow this to leak out of a set of domains.”
Almost akin to CORS where you specify where you want your thing to be
used. That makes sense to me. The issue for me, and not wanting to trod
over FPS over and over again, but the same party does not have the same
semantic meaning unless you approve of the FPS spec, and I don’t want
there to be a hard dependency on FPS in FedCM.

Kaustubha: yes, not trying to pull in FPS. But highlighting there are
different privacy properties where it’s still partitioned within a set
of domains vs. a global user identity.

Ben: a nice way of describing an IDP control and a great API
improvement.

Brian Campbell: the demo there showed a lot around UX and the account
chooser part of the UX. Is there a facility for interaction where the
IDP offers UI if there is no prior login that already exists? Some
factor that it may need to reestablish the auth? There’s a ton of use
cases where the IDP needs to take some additional action on a subsequent
sign-in. Not following where that sits in this stuff.

Sam: there is a UX affordance we’re introducing to log into the IDP
which is shown in the middle of the slide shown. Based on IDP sign-in
status API. Keeps track of is user logged into the IDP or not. If they
are not logged in, allow the IDP to log in in the IDP client area.

Brian: there’s cases where it’s not binary if it’s logged in or out.
Could be a session timeout. No opportunity to flip the status.Need to
just in time during the act of signing in render some arbitrary pages to
gather creds, reverify creds, do passkeys, you name it. I’m struggling
to see if it’s supported. If it’s not… it’s extraordinarily common in
both enterprise and consumer sign-in cases.

Sam: the IDP-controlled web page in the UX mock…

Brian: you say it’s keyed off of a status API…

Sam: Only if the IDP says to the browser that you logged out.

Brian: if you never logged in or your session timed out? Or during the
course of a signal intelligence check it needs to step up auth.

Sam: don’t know if we caught all of the corner cases, but went through
ones we expect. Probably didn’t capture all of them…

Brian: not corner cases, happens every day all the time.

Sam: sorry on terminology. Can send a link and work with you to see if
we covered the ones you’re referring to specifically.

Tim: let’s have that in a future meeting.

Brian: trying to look at current flows, a vast majority do something
based on a determination.

Ben: the counterpoint to UX concerns around popups, we’ve tried to train
users to look at the page they have loaded. Lifting UX on top of it is
another issue. Work to be done.

Sam: we know the challenges here, harder on mobile. Don’t feel strongly
on the specific UX mocks, we’ll learn as we go along.

Heather: that was helpful to put things in context for everybody. For
folks that are new to the group, I want to draw your attention to our
github repository and our use case library. “Where are 3p cookies in
common protocols, what about link redirects,” this is stuff we
documented a while ago. Documents our decisions about what things we’re
attempting to solve is covered in here. github.com/fedidcg. -
[<u>https://github.com/fedidcg/use-case-library</u>](https://github.com/fedidcg/use-case-library)
Also have a table on what 3p cookie mitigations do we know about. Also
relates to the decision tree diagrams; in a way it’s a different way of
describing it. You may find it informative.

Kris: if you have corrections, more info, feedback– that would be great.

Heather: thanks for good conversations on ways we can solve this. Our
calls are on Mondays. Mostly at 8am Pacific time. Every 4th call aimed
at APAC-friendly. We also have a Slack instance (instead of IRC). I’ll
send out an updated invite link. Enjoy the rest of your TPAC!

 

Attendees (sign yourself in)
============================

-   Heather Flanagan (Spherical Cow Consulting, chair)

-   Kris Chapman (Salesforce, co-chair)

-   Brandon Maslen (Microsoft Edge)

-   Cameron Boozarjomehri (Mozilla)

-   Chris Lemmons (Comcast)

-   Michael Knowles (Google)

-   Martin Thomson (Mozilla)

-   Ben VanderSloot (Mozilla)

-   Johann Hofmann (Google)

-   John Bradley (Yubico)

-   Vittorio Bertocci (Okta \| Auth0)

-   Sam Goto (Google)

-   Peter K (Google)

-   Erik Anderson (Microsoft)

-   Tim Cappalli (Microsoft)

-   Nicolas Pena Moreno (Google)

-   Sean Turner (sn3rd) - *observer*

-   Aram Zucker-Scharff (The Washington Post)

-   Rachit Sharma (IAB TL)

-   James Rosewell - 51Degrees

-   Yi Gu (Google)

-   Zachary Tan (Google)

-   Brian Daugherty (Google / Identity)

-   Chris Fredrickson (Google)

-   Brian Campbell (Ping)

-   Wendy Seltzer (W3C)

-   Tim Cappalli (Microsoft Identity, co-chair)
