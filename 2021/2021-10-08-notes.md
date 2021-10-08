-   Moderator: Kris Chapman

-   Scribe: Heather Flanagan

Agenda
======

Administrivia
-------------

-   Scribe volunteer(s) - Heather Flanagan

-   Reminders:

    -   [<u>Community Group Membership</u>](https://www.w3.org/community/fed-id/)

    -   [<u>W3C Code of Ethics and ProfessionalConduct</u>](https://www.w3.org/Consortium/cepc/)

User Stories
------------

-   User Stories - [<u>https://github.com/fedidcg/use-case-library</u>](https://github.com/fedidcg/use-case-library)

Kris: tried to make the topic generic, but it is based on experience at
Salesforce. They are using identity federation to give a single set of
credentials in order to use the service; it is not SSO.

George: when you talk about federation, you can sign into the portal
with my CNN credentials and then effectively that’s my authentication
into the portal, but the portal will assert my identity into the other
services?

Kris: yes. The administration page is doing an IAM aspect where it is
associating what’s going on.

George: it has created an internal identity for the user and pushes it.
There is an aspect of SSO, but the SSO is between the portal and the
services, and it’s federation between the user and the portal.

Vittorio: It sounds very confusing. This sounds like a keychaining
rather than a federation. The devil is in the details; how do you obtain
the token of all the other systems makes a difference. If you just have
refresh tokens on the server side, that’s one thing. IF you have to do
magic with iFrames or a chain of redirects before hand then that’s
another thing. It might make a difference, browser-wise, whether there
is tracking to be done and whether it is sanctioned or not.

George: Protocols matter. If the portal makes a SAML assertion and
shoves it to the RP, then it is just works. It is more complicated in
OIDC. Understanding the details is really important.

Achim: We don’t have something like this, but we have a setup that is
externally doing federation to RPs and internally doing federation via
OIDC to multiple IdPs. It just pushes through; you just authenticate to
your real IdP but it pushes through so it looks like a federation
service.

George: that’s probably another user story to add to the list.

Kris: Agree, the details matter a bit. Not certain that getting into
that level of details helps with what’s tracking and what’s not. That
makes tracking technically bound rather than the business case. From the
user perspective, what does this look like?

George: Of the services provided in the example, two are owned in the
portal but three are external with a relationship to the portal. From a
tracking perspective, what is the requirement of the portal to issue
pairwise pseudonymous identifiers to downstream systems? Does each
downstream system get a unique id for the user? What are the
implications from a business perspective for that to happen? Who’s
privacy policy is controlling the experience? Where is the tracking
happening, even in the business case? We need to determine that and then
we can figure out if it’s sanctioned or not because we can determine if
the user understands what’s happening.

Kris: OK, let’s look at details. There will probably need to be a whole
set of unique user stories.

Sam: Want to +1 what George said, but not sure it’s in disagreement to
the business perspective. To paraphrase what I heard: you can think of
this from a tracking perspective, from a business/user comprehension
perspective, what’s the worse that can happen if the parties collude
with each other? What surprises would a user go through, assuming the
email management company is also a different company and colludes with
the chat services company? That’s the delineation between sanctioned and
unsanctioned. May also want to ask what kind of surprises a user wants
to go through if an IdP knows what services you use.

Kris: didn’t fall on either side of the details; what I took away from
George and Sam is that we should spit on the technical details as they
differ on the tracking perspective. We don’t want every possible
technical technique in every user story if the tracking is the same.

Tim: one of the details I’m interested in is hearing whether the IdP
gives a directed identifier, and if the user actively chooses to provide
it after the sign-in flow, is that sanctioned? If I as a user go into my
IdP and say “I always want to share my real email” is that sanctioned,
or is that still a per sign-in flow consent?

Sam: the mental model I have is whether the user is caught by surprise.
That’s what separates the situation. If the user shares their email
address with the RP, the user has an intuition that they are sharing it
for the purposes of communication. If the company wants to talk to me,
this is a way they can communicate with me. What is less clear is if the
different websites uses that same email address for purposes other than
for emailing me, that falls into the “catches users by surprise”.

Tim: I think this is where we differ. This isn’t a technology problem;
this can’t be solved in the browser. This is so far beyond the
federation problem. If I as a user go into store 1 and give them my
address, and go into store 2 and give them my address, I know they both
have it.

Sam: I am not making a presupposition about the solution of the problem.
I want to focus exclusively that when I share my email address with a
website, that I don’t expect the website to have the ability to have my
activity in this website joined with my activity in another website.

Achim: To me they are two different pieces in the discussion. One piece
is there is an information flow for the purposes of signing in. That’s
what’s happening in the protocol flow, and typically an IdP and an RP
has some agreement in how that’s structured (legal agreements, etc).
It’s a mixture of service agreement with users, approval of users, and
T&Cs. The other bit is the discussion around directed identifiers - what
might happen afterwards with information provisioned to an RP. Tim’s
point that this is what happens after and might be out of band; the
framing for this involves consent, or not. They are two separate problem
spaces with separate flows of information. I also think that the user
may have an expectation that logging into a site should be a separate
action, and any other data processing should be a separate choice and
that’s nothing we can fix in the browser. There might be a default way
(everything directed) but there are other things that happen outside the
browser where one, at a point of time, you leave the realm where the
parties that engage with the user what the separate choices are.

George: Like the designation of identification of problems, and then
determining if this is a problem that’s reasonable for this group to
solve. Is this something that’s viable for this community to try and
solve? So I’ll add one other problem in the unsanctioned tracking kind
of a world, and we can decide whether it stays. I provide an identifier
like a phone number that is being used for fraud prevention. The site
takes the mobile number and goes to a data aggregator to collect more
information about me for targeted ads. Is that an unsanctioned tracking
kind of a problem? Because it falls into the scenario of what happens
when data is shared with downstream systems.

Giuseppe: In the context I come from, I use both SAML and OIDC. The
privacy issues I find on in traditional SSO are: once authenticated with
an RP, the user that relies at another RP can be automatically
redirected for authentication (when they have not previously requested
to review the consent page every time). So the RP will be aware of the
user each time without the user being aware of it. The other problem is
that an IdP manages to correlate the identities with the services they
consume.

Achim: It is fair to say that, based on what George was saying, is that
it’s related to identity but it may happen offline. It’s fair to say
it’s a related problem and the question is whether it’s in scope to
solve it. Any fix leads to another unintended consequence for the user.
What Apple does with anonymized email addresses mean the user can create
dynamic email addresses, and from a tracking perspective, is the user
aware that all their emails are routed through another party before
getting to their inbox?

Sam: That’s a wonderful observation. Want to go back to a framework for
work in this group. Solutions to one problems may raise other problems.
Some of them can be privacy-related, or customer-service-related. So
it’s key that we talk about problems and not solutions. If we can agree
to problems, we can shop for solutions, comparing and contrasting on
what offers the best balance. Going back to Kris’ specific problem, when
a user logs into an RP, in that moment they are agreeing to logging into
that RP and, often, also having communication coming from that RP via
email addresses. That’s control and transparency for the user, and
that’s important. What I want to establish as a problem, which may or
may not be relevant to this CG, at that moment, the user is neither in
control nor aware of when they share their email address to different
RP, they can collude behind the scenes and build a richer profile. The
problem is the collusion that the user is not aware nor in control of.

George: If the point is to look at where can there be privacy problems
with existing identity flows, noting this is the federated identity
community group, we can consider whether we can solve that problem to a
reasonable level of usefulness in a federated scenario. Not so much in
this issue; this issue seems more like an IdP-initiated flow. From a
legal perspective, the flows are covered. But the user’s understanding
of the legal implications are not clear. Is that transparency something
we can solve at the protocol level is a question.

Kris: Agree with that. Fundamentally, I have a concern about basing a
lot of this as to whether a user understands because that’s such a wide
spectrum of what people actually understand. In the use case we’re
discussing, this user that’ slogging in has set up an account and should
know that every single RP knows who they are and yes, can use that email
address because they are working with us as a single entity. So them
being surprised when logging into that portal and the RPs can work
together is not something that would be surprising to users. We need to
separate this out and figure out what we tackle and what we don’t. We
need to make sure users are aware, but we also are not here to protect
users from themselves.

Allan: Like the idea of ‘surprise’ but would take it a little farther
than Sam does. If the info I provide is used for anything other than
authenticating me, even if it’s my email address, then it’s a surprise.
To the extent we can build safeguards to keep the information I provide
to the IdP from being used for anything else would be a good direction
to go. One other use case that some people have that I would not
consider sanctioned is when companies that work with the IdP and that
you can log in to with that IdP but you don’t actually do so, and yet
they can collect data, then that’s a problem.

Achim: If we can agree that it’s fair to put this in a problem
description and then discuss whether it’s worth fixing or not is good.
If the third party service is for fraud protection, is that good? If the
user gives their email address, they might expect it to be used for
account recovery but not for product sales? There will always be parties
that misuse information, but we can’t prevent that.

Vittorio: I’m concerned about the direction the discussion is going. We
know this stuff is prone to endless philosophical exploration. The goal
of this CG is to make sure that whatever happens in the
privacy-preserving world don’t screw around with the federation
scenarios already accomplish today. We started well with “here’s the use
case and here’s what we collect and use from the user”. What’s happening
downstream is more for the privacy cg. For us, we understand we
understand they are the generic case for privacy, but here’s where we
need to have an exception, a dialog, some mediation, for federated
identity to work. The value of the group being fed id is to focus on
what fed id needs. The potential for abuse are interesting, but I
wouldn’t start with those.

Kris: definitly agree. It is very important that we define what we’re
dealing with and what we’re not. Want to put in a plug for people to
submit use cases because that would be the most useful for what we can
get from this.

Sam: +1 Kris’ assessment of does it catch the user by surprise. If you
don’t think it catches the user by surprise because of the organization
structure, write that down. We don’t think this is catching the user by
surprise because the user understands the org structure. The use case
also notes that some of the entities involved are not under the same
legal structure; maybe that’s a separate use case? Ultimately, it’s your
determination to delineate the properties. Also, to respond to
Vittorio’s point - very valid point. From a sequencing perspective, what
order and whether we solve problems is a fine conversation to have, but
want to go back to find the most primitive, minimal thing we can start
from. The most minimal thing we can do is whether we agree on whether we
agree on the why (the problem). Do we agree this is catching the user by
surprise or not? It is a bit philosophical, but it helps us make further
decisions.

Tim: Question about the use case template, should we be adding a call
out about whether this user is engaging this relationship as an employee
or an individual?

Kris: yes

Heather: would also like to add to the template “Do you, as author of
this use case, think the user in this scenario is caught by surprise?”

Kris: yes, and please submit your use cases

Vittorio: next week is IIW. If there is enough participants from this CG
there, maybe have a session there about this (and attract new members to
the CG).

Heather: next week is a regular CG meeting. Will be talking to Kris and
Tim to build the agenda

Sam: While this feels philosophical, it is the same process we followed
to get to our privacy threat model in Google. Also want to separate a
threat model and mitigations. Heather Flanagan

Brian: Great discussion. Find that these discussions are more productive
if we focus on proposed solutions, then proposed issues with that
solution, then mitigations around those issues. Would also suggest that
if we could vote on use cases and decide as a group what would be the
most useful to consider as a group would be helpful.

Vittorio: We are starting from very different positions. For me,
federated identity words today for it’s intended purposes. The fact that
the IdP knows what the user are doing are facts of life, covered by
EULAs. It works today. Unless legislation comes out that says this is
unacceptable, then we do not want to change it. There are privacy
challenges we need to tackle as an industry, but in fed id, I’m not
thinking about the identifiers my users are using. I want to make sure
that whatever is done to make sure the user knows what’s happening with
their data does not impede expected federation flows.



Attendees
=========

-   Heather Flanagan (chair, scribe)

-   Tim Cappalli (co-chair)

-   Kris Chapman (co-chair)

-   Achim

-   George Fletcher

-   Allan Spiegal

-   Vittorio Bertocci

-   Sam Goto

-   Brian Campbell

-   Brian May

-   Giuseppe De Marco
