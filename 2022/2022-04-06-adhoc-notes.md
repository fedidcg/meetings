# FedICG ad hoc call - 6 April 2022

-   Moderator: Heather Flanagan

-   Scribe: Heather Flanagan

Agenda
======

Administrivia
-------------

-   Scribe volunteer(s) - Heather

-   Reminders:

    -   [<u>Community Group Membership</u>](https://www.w3.org/community/fed-id/)

    -   [<u>W3C Code of Ethics and Professional Conduct</u>](https://www.w3.org/Consortium/cepc/)

 Attendees:

 Discuss
 [<u>https://github.com/fedidcg/use-case-library/wiki/Third-party-cookie-mitigations</u>](https://github.com/fedidcg/use-case-library/wiki/Third-party-cookie-mitigations)
 via working doc
 ([<u>https://docs.google.com/spreadsheets/d/1R9UDAczDaSASO-s6VxWuiCye0RxILsSjJYRYpLElJSw/edit\#gid=0</u>](https://docs.google.com/spreadsheets/d/1R9UDAczDaSASO-s6VxWuiCye0RxILsSjJYRYpLElJSw/edit#gid=0))

 Vittorio: session management is ambiguous term

-   opening an iFrame on your RP is something people do, but isn't in a
     standard nor is it particularly common. It's a trick people use,
     and has nothing to do with OIDC session management ("cottage
     industry" session management)

-   there is also an [<u>OIDC session
     management</u>](https://openid.net/specs/openid-connect-session-1_0.html)
     standard, which is difficult to package in an SDK so is also not
     particularly common (as far as we know)

 Brian: not super widely deployed; our products don't support it. It's
 not really session management as much as it's a notification of
 session changes

 Vittorio: some people do use that to determine if the session from the
 IdP is gone and therefore signaling sign out to the RP, so it becomes
 a form of session management. And most people do this because they
 want to keep a session alive, not because they want to pro-actively
 sign out.

 Sam: it would be informative to set some priorities in the protocol
 primitive table to know which things are actually important to
 mitigate. Which rows matter more than others, so browser developers
 can make their tradeoffs.

-   Heather to take an action to follow up on this

 Vittorio: in terms of priority for the 3pc mitigation, the ordering
 would be front-channel logout, background refresh token, "cottage
 industry" session management, OIDC session management

 Heather: so what on this list does not solve for front-channel logout?

 Sam: Storage Access API will, with lots of prompts

 Kris: Storage Access API will only work in some cases

 Vittorio: what I heard was the ordering of when you make the call to
 storage access API means it may not work at all for logout.

 Kris: we have managed to make it work, but it is very particular in
 how to make it work. There is a timing issue.

 Ben: we have run into this as an issue, but trying to piece this
 together with how front-channel works to see how it applies directly.

 Sam:
 [<u>https://openid.net/specs/openid-connect-frontchannel-1\_0.html</u>](https://openid.net/specs/openid-connect-frontchannel-1_0.html)

 Vittorio: if you sign into two different web apps, and you are in
 application A and want to sign out, A will get rid of its own cookies
 and then send a message to the IdP and say "it's time to sign out any
 session provided on this guy" and that will render a set of iFrames
 and present the cookie to RP to get them signed out.

 Ben: we have heuristics on that; each embeddd party will get up to 5
 free storage accesses before hitting users with the prompt. In this
 case, the RP would be the embedded party and be able to get through
 this for free, but there would be friction.

 Brock: Would like to see that description here so, as a developer, I
 can see how this should be implemented.

 Ben: Storage Access API is a javascript api on the document object,
 you'd call that inside an iFrame, and that gives you access to
 unpartitioned storage. IF there is blocking of 3pc or storage it gets
 around that.
 ([<u>https://developer.mozilla.org/en-US/docs/Web/API/Document/requestStorageAccess</u>](https://developer.mozilla.org/en-US/docs/Web/API/Document/requestStorageAccess))

 Brock: a lot of these things depend on the nature of the app; if you
 build a client side app vs a server side app, it totally changes how
 you implement these protocols. The context of the solution depends the
 app itself.

 Vittorio: we're already operating at the grant level; the moment you
 do front-channel logout, the style of app doesn't matter.

 Brock: that's why I need a more technical explanation of how this all
 fits in.

 Sam: There is a column in this table that refered to backwards
 compatibility. In the Storage Access API is that it's backwards
 incompatible with RPs; it requires RPs to serve new HTML.

 Kris: I can write in some of these technical details; what we did
 worked with Firefox but didn't work with Safari because Safari
 required more direct user engagement. Backwards compatibility is not
 just RP, it's also browsers. The details I can add will only be what
 I've been exposed to; don't necessarily want to say that's the only
 option

 Sam: still useful to note that down (your deployment experience). If
 all of us did that, we'd find commonality in terms of what tricks
 we're using, and the norm would emerge.

 Kris: should this be a dedicated page, or go in the table?

 Heather: dedicated page, then others can add their own experiences

 Tim: understand the perspective from the browser side, but from the
 identity side, the privacy impact is different depending on your
 perspective. Identity people see that this allows browser to track
 something they've never tracked before.

 Vittorio: right now we're talking about front-channel log out, but for
 FedCM, the spec suggests there is actually a significant RP impact in
 that they have to change how they handle identity and so that's a big
 lift. If it's just experience at the prompt side, then yes, little
 impact.

 Sam: still stand by this is possibly "none" for the RP; the prompt
 would be at the IdP, not the RP, at sign up or sign in at the IdP
 level, and then the RPs wouldn't have to do anything.

 Vittorio: if you manage to do that, fantastic, but if it's only a
 possibility that's not in the implementation or spec yet, we need to
 be clearer in this table.

 Sam: we have a PR for this, but it isn't in origin trials yet because
 we don't have a design partner to help us test.

 Vittorio: so make the statement the RP doesn't have to change for this
 flow, you can do that without a partner; the protocols are well
 documented and you can set up a fake endpoint that behaves like a
 typical RP and test with that.

 Sam: probably a tangent; let's discuss another time; want
 specifications to follow implementation and not the reverse

 Heather: for FedCM, in this table is it only considering front-channel
 logout?

 Sam: we've read front-channel logout enough that we're confident that
 we'll solve for that, but not as sure about the other two

 Vittorio: if the trick you're using in an iFrame that will allow the
 RP to get the cookies for logout, then it will also work for the other
 issues

 Sam: my intuition says that's true, but want to have a more concrete
 answer

 Kris: this goes under the privacy impact column - has anyone (IdP) had
 their legal teams looked at the DMA? It's aimed at big tech platform
 and is geared towards preventing big tech from tracking across
 services. DMA concerns may need to become its own concern.
 [<u>https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=CELEX:52020PC0842&from=en</u>](https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=CELEX:52020PC0842&from=en)

 


Attendees
=========

-   Ben VanderSloot (Mozilla)

-   Cameron Boozarjomehri

-   Vittorio Bertocci (Okta\|Auth0)

-   Kris Chapman (Salesforce, co-chair)

-   Heather Flanagan (Spherical Cow Consulting, chair)

-   Sam Goto (Google)

-   Kaan Icer (Google)

-   Yi Gu (Google)

-   Brian Campbell (Ping)

-   Tim Capalli (Microsoft)

-   Brock Allen (Duende)
