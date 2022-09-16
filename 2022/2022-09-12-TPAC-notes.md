# FedID CG TPAC 2022 Day One

-   Moderator: Heather Flanagan

-   Scribe: Nicolas Pena Moreno,

Call-in details: see
[<u>https://www.w3.org/events/meetings/90dfd3a8-b42b-4981-a09f-d911e8959257</u>](https://www.w3.org/events/meetings/90dfd3a8-b42b-4981-a09f-d911e8959257)

Charter:
[<u>https://github.com/w3c/fedidcg</u>](https://github.com/w3c/fedidcg)

-   

Notes
=====

Charter conversation
--------------------

Heather: It's time to review the charter. Here are some highlights.

-   We want to prevent untransparent, uncontrollable tracking while also
 enabling federated identity on the web. This means balancing
 privacy concerns as opposed to 100% prioritizing privacy concerns.
 Short-term goals are prioritized based on the urgency of changes
 underway, such as phasing out of third-party cookies. Link
 decoration is going to be an area of even bigger concern to us
 because OAUTH, OpenIDConnect and SAML rely on them.

-   Our scope is user features and APIs. Out of scope was redesigning
 federated identification. That’s not what we’re here to talk
 about, but rather about federated identity on the web. Ad-tech
 tools are also out of scope.

-   Deliverables: we want to talk about what the users need as well as
 what developers need. That turns out to be a little bit harder for
 some. But there needs to be room for innovation and potentially
 failing.

-   Work items: FedCM, decision tree documents, and any important output
 of the group. How many of you know the difference between a CG and
 a WG? We are a CG, so one of the things we think about regarding
 work items is ‘when is this ready to migrate to the next step?’

-   Discussion time: are the goals we have still correct, i.e. should we
 continue focusing on third-party cookie issues?

Kris: I’m one of the co-chairs of the FedID CG and represent Salesforce.
I personally think that third-party cookies made sense before, but since
Chrome pushed out the timeline, perhaps we should expand the scope.

Vittorio: I think the group did a good job of identifying strategies to
prevent breakage but need to wait and see if they work in production. I
also agree with Kris that it makes sense for us to expand our horizon.
Cookies are solvable, whereas other issues are more critical and harder.

Martin: Is the charter currently updated to reflect the work items that
you listed?

Heather: no, I have not updated.

Martin: I would like to suggest that this group consider becoming a WG.
This group is doing WG work, and not CG work.

Heather: Do you think we need a dedicated WG or should it go to
WebAppSec?

Martin: My intuition is that we want a dedicated one. I do understand
that there are IPR restrictions which makes us want to find another WG.

Heather: Sam, do you have an opinion?

Sam: regarding talking beyond third party cookies, that matches my
intuition. I think we have fewer blindspots there, even though we still
have some questions, i.e. we should not consider it done. Now we can
expand to bounce tracking and link decoration. Because it has such a
massive impact on federation, I think it is worth getting involved
early. But there should be a balance, as there will be user flows broken
when third party cookies go away. Regarding WG, that matches my
intuition too, and I personally support that move. Jeffrey is one of our
experts, and Rick here also has a lot of experience. I don’t personally
feel strongly between WebAppSec vs here.

Jeffrey: That all seems fine.

Heather: FedCM does not solve all of the third party cookie use-cases.
Is there anything left that you think FedCM should be solving?

Sam: We think of it as a tool, which can be expanded to do some other
jobs. It’s not a hammer, and should serve the community as needed. There
are certain things that we don’t know how to solve. Front-channel logout
remains to be a problem that I think FedCM has a solution for, but we
haven’t gathered enough deployment experience to be confident. And this
problem is urgent as it is needed by IDPs, but it is not one we are
confident about. We don’t have a better option so far - maybe Storage
Access API.

John: One of my goals today is to bring the login status API to this
group, which covers the logout scenario and is broader than federated
login. We were planning to bring this conversation here.

Martin: There are a number of issues on the spec as it relates to
authorization.

Ben: I think we should try to resolve an answer for third party cookies,
and looking at the decision tree diagrams, FedCM does not solve all the
cases. From Mozilla’s perspective where we have deprecated third-party
cookies, there are various heuristics we have to use to account for
breaking scenarios.

Kris: Similar to Ben’s feedback, I would say that FedCM should have a
lockdown on what it expects to handle and what it doesn’t. FedCM is
thought of as the answer to federated identity without cookies, but it
is not.

Ben: Would we like FedCM to have broader application scope, or do we
need a new work item to address other third party cookie issues?

Heather: When we talk about what our charter needs to cover, what I hear
is that third party cookies are still a priority, and we may need to be
agitating outside work for things that need to happen. One of the
confusions we’ve had last year is trying to make FedCM solve everything.

Vittorio: In an ideal world, we have a solution where everything still
works in a privacy preserving manner. But I think in-flight the scope
changed. Early on, there was a proposal where there would be
interstitials to inform the user of what was happening. Unclear if we
need to preserve everything. When Chrome becomes strict about cookies,
we will discover if we failed.

Sam: In agreement that we want to prevent tracking on the web, while
minimizing deployment hassle for IDPs and RPs. None of the variations
that we looked at early on with FedCM are out of the table. They have
different properties. We prioritized mediation, but we can certainly
look at the other two: delegation and permission. Delegation has some
good privacy properties, and permission helps a lot with backwards
compatibility.

Heather: As you may recall from the decision tree, we point to a lot of
work that is happening in the privacy CG. Does anyone have suggestions
on how to collaborate effectively?

Kris: One possibility is to have a WG that handles both privacy and
federated identity. It is a little scary.

Sam: The intersection is Storage Access, bounce tracking mitigations,
First Party Sets, CNAME, and Fenced Frames.

Kris: Maybe even Trust Tokens.

Theresa: That would require a lot of experts to join a big WG. So I
think a more scoped WG would be better. (Sorry I jumped the queue.)

Kris: We’ve been struggling since we need federated identity folks,
browser folks, and privacy folks working together to solve this problem.
This is a very global problem with diverse implementations and
expectations.

Ben: I think if this isn’t the set of people to discuss this, I don’t
know who is. Maybe more frequent discussions in Privacy CG can help, but
I don’t think there is a magical thing we can create to solve this.

Kris: We need some merging.

Heather: There was a workshop a few years ago asking whether we needed a
new group. FedID CG was born out of it, and that is why we ended up in a
different space. We need to do a better job communicating with the
Privacy CG.

Vittorio: I’m very biased, but I think the charters are very different.
For me largely what this group is about is preserving the ability to do
federated identity. I’m ok with Privacy CG doing the privacy
considerations. I don’t worry that much about the privacy
characteristics of federated identity. Everyone enters a contract
willingly, and privacy implications are baked in. I’m more concerned
about the mechanics and what breaks and what doesn’t. If we try to
manage the two, progress will be difficult. I think there should be one
group pushing for one thing and the other group pushing for the other
one.

Heather: One of the words you used is preservation. I worry that when we
talk about preserving federated identity, there is occasionally a
misunderstanding about preserving functionality vs preserving the code
flows. We all agree preserving is important. But I don’t think we agree
about what we’re preserving.

Kris: Are we expecting to evolve to the final state?

Heather: One of the things is that we’re not trying to write identity
protocols. We’ll keep that as out of scope. But we should talk with them
so they know what’s happening. 10 minutes to break, any other comments?

Sam: I think it may be constructive to have in the charter that a goal
is to minimize deployment challenges, but the privacy constraints are
harder. Deprecation of third-party cookies is not backwards compatible.

Vittorio: There is a strategic time horizon. We do our best but no one
can expect that we’ll never have to change anything.

Jeffrey: It is probably worth writing in the charter that this group
wants to write a WG charter.

Bounce Tracking Mitigations
---------------------------

\[[<u>Slides</u>](https://docs.google.com/presentation/d/1zGN4Mwti3H2UATa3s2fgAYsIKAlxC63SbDMWU6vaHsA/edit?resourcekey=0-qmIzIHCgMHEdF8YjuxnWqg#slide=id.p)\]

Ben Kelly: Working on Privacy Sandbox, currently thinking about what can
be done on bounce tracking.

-   What is bounce tracking? Method to simulate third-party cookies
 using a first-party context. Navigate to another site, fetch
 first-party cookie, navigate back.

-   Can be “bounce back” to original site, “bounce through” to a third
 site.

-   Other browsers already have solutions, documented in PrivacyCG
 Navtracking mitigations report:

    -   Safari identifies redirectors and caps cookies to 24 hrs.

    -   Firefox removes storage from trackers after 24hrs unless user
     has interacted with state.

    -   Brave maintains a list of trackers and immediately deletes
     storage unless they had prior state.

-   Chrome: [<u>Explainer
 out</u>](https://github.com/wanderview/bounce-tracking-mitigations/blob/main/explainer.md).
 Goals:

    -   Converge on a solution

    -   Consistency, if possible avoid lists

    -   Avoid breaking non-tracking use cases, example SAML.

    -   Handle short-lived domains that may evade list-based approaches.

-   Chrome Proposal:

    -   Detect “stateful bounces”, chain of server- or client-side
     redirects.

        -   May include all redirects (because network stack itself is
         stateful) or only accessing storage.

        -   Avoid tracking lists or behavioral classification.

    -   After some time (x hours) delete storage for site that was
     bounced through…

    -   Unless we determine the user has purposefully chosen to use that
     site:

        -   Previous interaction (up to x months to a year, Firefox uses
         45 days, Chrome would prefer longer)

        -   Open to other signals

-   Non-Tracking Use Cases to be protected

    -   Authentication / SSO - hope that past interactions will handle
     this

        -   Looking for feedback (Vittorio shaking his head) from this
         group on whether this will be protected.

    -   Payments

    -   Link Shorteners Measuring Unique Visitors

    -   Looking for more feedback on more use cases, main goal for
     Chrome this week is to get this feedback.

-   Comparison:

    -   All mechanisms are very similar, exemption for interactions is
     very much like an exemption for prior state. Feels very close.

Vittorio: Great, creating framework for comparing different approaches.
Main thing that came to mind about interaction being the exemption. SSO
is the opposite of this! You are describing the first interaction. Works
for first interaction. But now, I go to website two… website two
redirects to SSO, and does nothing. At that point, there was no
interaction. If you have a way of taking this into account, then great.

Ben Kelly: Clarify, we aren’t allowing the interaction to be during the
bounce. The fact that you clicked anytime within the last year, or six
months, means we won’t delete the storage. Does that address that
particular scenario?

Vittorio: Yes. Then it becomes a matter of timing. A newspaper wants
this to last forever, so you need to negotiate, can’t be forever, but
for companies that often want to authenticate often, this will certainly
work.

Ben Kelly: For me, I am ok with forever.

Nick Doty: Curious about interaction, thank you for overview. Concerned
that in many contexts, this will be an incentive to re-use that domain.
If you have a popular domain, from social media perhaps, you can re-use
it for bounce tracking.

Ben Kelly: Mentioned in explainer, any site with a great deal of
first-party activity. We do not view this as the end, in terms of
solving navigational tracking. This is one piece. This solves the issue
of a long tail of sites that fly under the radar. Big sites could get a
lot of scrutiny if they start using their primary domain for bounce
tracking it will get notice; there are disincentives for doing this. I
agree with the issue, I think it’s real, and we are open to ideas about
it, but we think this has a part to play for the long tail, and very
consistent with what Brave and Firefox are doing and their mitigations
have the same weakness. Different concern, something needs a different
solution, and there won’t be a one-size fits all.

Nick Doty: Understand, not sure if I share your perception about
scrutiny.

John Wilander: When you’re talking about deleting website data, is it
bouncer domain’s website data or the destination website?

Ben Kelly: Bouncer.

John Wilander: If there has not been interaction, 5 year old behavior,
then it deletes all storage on the bouncer after 1 hour. The destination
is what’s capped at 24 hours. Followup question about interaction?
Safari uses 30 active days of interaction, worried that if it’s too
long, then there’s a incentive for trackers to make interstitials.

Ben Kelly: Time is not decided. We are worried about motivating
interstitials. It’s not a slam dunk, though. Users now have some ability
to notice the interstitial, “I was on this site and it went me to some
other weird site that I didn’t ask for”. Some friction added for their
users, not clear to me if interstitials would proliferate or not,
because there is some back pressure. If we saw interstitials, we might
add a list based approach.

John Wilander: At least one known case of a 1p that gets used regularly,
engaged in bounce tracking, where the interaction doesn’t help. Deployed
some code to rewrite all of their cookies to SameSite Strict. The site
then backed off of that approach.

Ben Kelly: A list of one?

John Wilander: Yes! There aren’t many of them, popular websites that
also try to do bounce tracking.

Kris Chapman: Software as a service is often in this situation, we are
very much not trying to create interstitials. Basically offering as a
web service or a database, providing a service that looks like first
party but is a third party. We often have to tell users “This doesn’t
work on Safari, you have to use Chrome”, we do not want to be in that
position. Interaction as an indication that the user is expecting to do
these things is very focused on this B2B, B2C aspect of a user going to
a website to interact with content. But many users are going to a site,
that site is using utilities, analytics, etc, that the user isn’t aware
of (but are in service of the first party). Fundamentally a problem, the
problem with federation, the IdP is not the RP. On these things, we’re
getting pressed towards CNAMEs where we make it seem like its a first
party, downside of removing visibility to the user. Or we do things
server-to-server. I don’t think either of these is great for privacy
users. We are looking for things where the site that’s being visited has
a say, ‘these are my vendors’.

Ben Kelly: Third party context, embedded iframes, I understand this
issue. But here, we have a site trying to make it appear that a user has
visited a site in the top level. To me, that is different than saying
you want to be a supplier on a site, in that use case it would make
sense to have less rights than a site that was in a top level.

Kris Chapman: Tableau is a good case of being top level, but maybe
having a NYTimes login. No consistency of how these things are deployed:
iframes, inline. \[Will cover other cases offline\] L'oreal & Maybelline

Charlie Harrison: The predictability is really important here, but also
seems like the proposed solution, an interaction requirement, is a
classifier style approach. I would encourage us to think about how we
can make that as predictable as possible, the concern for some of these
use cases, maybe Vittorio was commenting on this, if we set the time
threshold to T and deploy it, you’ll see breakage for a tail of users
who don’t do the interaction pattern you expect. Hard to debug, hard to
deploy solutions around, I think we should try to aim these solutions to
provide transparency as to whether you’re being classified, telling you
why you had something deleted, and maybe trying to explore alternative
signals that are visible to you (webdev). Feels like interaction may be
a noisy signal depending on use case.

Ben Kelly: Curious to hear what other people believe is a simpler
solution. There is history for using this mechanism.

Chris Lemmons: Trying to debug something mysteriously disappearing will
be very hard, so transparency on that process would be valuable. \[Ben:
Devtools or API?\] Devtools, be neat if the console told me… I worry
about domains on which multiple people have control, such as
s3.amazon.com. There is an incentive to get yourself on the
hasInteracted lists, and I worry that shared domains like this can end
up a target in a way that they wouldn’t for a list-based approach. The
threat model is a site that is under control of multiple site owners…
\[John Wilander\] gave an example of a site which had two purposes, that
could happen with \[user content\].

Ben Kelly: Yes.

Chris Lemmons: May be underestimating how tricky interstitials can be.

Ben VanderSloot, Moz: Will talk about what he doesn’t like about Mozilla
and what they do. User expectations are not always clear—when doing
research, he’ll visit the first party site of trackers, which
compromises his privacy. Hard for users to get a good grasp of this.
Does encourage centralization, interesting dynamic and tries to oppose
centralization forces. But overall, I think as a thing to standardize as
a short term solution, this makes a lot of sense, and that will make the
developer expectations a lot clearer. Be good to align closely, quickly,
and then move onto better solutions like the ones we might create in
Fed… that target this use case more precisely. The purpose-built thing
would be way better than an activation-based heuristic. If you want
better indicator, we’re trying to build it here, I promise.

Ben Kelly: As I understand it, if FedCM even if it was done will take
years to get adoption.

Ben VanderSloot: Yeah, short term can be months to years, just mean this
is not a desired end state.

Erik Anderson, MSFT: Comment on short-term vs long-term, would be nice
to think through what long term would look like. Long term, browser
could insert an interstitial that something funky is happening. Could
not send state based on an attribute in the anchor tag. Be nice to come
up a list of things, give people a long term understanding of, over time
as we ramp up bounce tracking protections, things will change and you
should get in touch with FedCM so that things go smoothly down the road.
Pointing to the S3 case, it does seem valuable to have a heuristic that
is predictable but better than interaction.

Johann Hofmann: Don’t want to overload and add too much to this
proposal; I think it’s fair to say “this is outside of our threat model”
and if we add too much to it we can quickly end up with something that
can’t be implemented for 5 or 10 years. Prefer to have something
achievable short-term, simple. If we want to have better signals, we
have to build it, and maybe enable developers to know about it.

Kris Chapman: Feedback is to not rely on just one signal. Nice to have
multiple signals to dial in \[on right behavior\].



Attendees (sign yourself in)
============================

-   Sam Goto (Google / Chrome)

-   Rick Byers (Google / Chrome)

-   Nicolas Pena Moreno (Google)

-   Christian Biesinger (Google)

-   Ben Kelly (Google)

-   Peter Kotwicz (Google / Chrome)

-   Jeffrey Yasskin (Google Chrome)

-   Michael Knowles (Google / Chrome)

-   Kristen Chapman (Salesforce, Co-chair)

-   Martin Thomson (Mozilla)

-   Nick Doty (Center for Democracy & Technology)

-   Cameron boozarjomehri (Mozilla)

-   Benjamin VanderSloot (Mozilla)

-   Tim Huang (Mozilla)

-   Brandon Maslen (Microsoft Edge)

-   Russell Stringham (Adobe)

-   Zachary Tan (Google / Chrome)

-   Brian Daugherty (Google / Identity)

-   Erik Anderson (Microsoft Edge)

-   Sam Weiler (W3C/MIT)

-   Jonathan Njeunje (Google)

-   Brian Lefler (Google Chrome)

-   Vittorio Bertocci (Okta)

-   Kaustubha Govind (Google Chrome)

-   Yi Gu (Google Chrome)

-   Johann Hofmann (Google Chrome)

-   Theresa O’Connor (Apple, TAG)

-   John Wilander (Apple)

-   Charlie Harrison (Google)

-   Shubhie Panicker (Google)

-   Chris Lemmons (Comcast)

-   Sean Turner (sn3rd)
