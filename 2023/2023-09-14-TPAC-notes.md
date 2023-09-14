# FedID CG notes, 14 September 2023 (TPAC)

## Agenda

* Welcome & Administrivia (09:30-09:35)
  * Scribe volunteer(s)?
  * Reminders: 
     * [Community Group Membership](https://www.w3.org/community/fed-id/)
     * [W3C Code of Ethics and Professional Conduct](https://www.w3.org/Consortium/cepc/)

* Working Group charter discussion (09:35-10:20)
* Open issues for FedCM (10:20-11:30)
  * Decision required
    * Login Status API - align on [breakout](https://github.com/w3c/tpac2023-breakouts/issues/61) results
  * Other open [tickets](https://github.com/fedidcg/FedCM/issues)?

* Combo meeting with Web Payments WG (11:30-12:30)
  * Open Q&A

* AOB (12:30-13:00)

## Notes

Scribe: Nicolás Peña Moreno

### Charter discussion

* Tim: original thinking was that this WG would be chartered for some of the wallet work. But that work has not been incubated yet. So this charter would talk about FedCM only, but open to adding the other stuff later. How many people read the charter? (A few hands)
* (Some time reading the charter)
* Sam: mostly questions for Mozilla to see how they feel about this. Is it soon/late or anything they want to see done before moving to WG?
* Martin: I appreciate that this is happening. I think this is the right scope
* Sam: I’m curious to hear if John has any intention to join the WG
* John: login status in itself might need a WG so that might be the quickest way to make it happen. Other than that, don’t know when we would plan to implement FedCM.
* Sam: That is currently in Privacy CG. Would we add it as an item?
* Tim: Yes, we can do that.
* John: I am fine with that.
* Martin: same.
* Sam: We meet the requirement of two browsers. There is also the requirement of two identity providers.
* Tim: Do we want two company-independent providers? In any case we will be involved. I do know one of the IDPs involved is not a W3C member. But the other one is a W3C member.
* Sam: Gina can represent Google sign-in. I’m not sure if they typically come to these, but would they join?
* Gina: Yea I’d be open to join.
* Tim: It would be nice to have someone representing that part of Google explicitly.
* Sam: Is it more of a suggestion or hard requirement? I.e., do we need to proactively find IDPs and RPs to join? I know specs need at least two implementations.
* Tim: Yea we added that.
* Achim: The text is open.
* Sam: It does say that. “To be successful, this Working Group is expected to have participation representative of at least two of each of the following: large-scale Identity Provider (IdP) operators, large-scale Relying Parties (RPs), federation operators, and two browser vendors.”
* Achim: I think that makes sense.
* Tim: I think we can meet these on paper, but do we want that in there?
* Achim: This might help get parties involved. Seems doable.
* Sam: In my experience, engaging with the RPs is sometimes through the IDPs.
* Achim: Yea. Seems easy to fulfill.
* Sam: Relationship between WG and CG. Will we maintain the CG?
* Tim: Early discussions happen in the CG. They can graduate into WG.
* Achim: Seems sensible also in relation to the question of membership. Besides GitHub being open of course.
* Sam: How would the promotion cycle look like?
* Achim: The charter has been handed over to the strategy team.
* Tim: I think that is for us to define.
* Achim: If we get consensus today, it would be about January when the WG is created.
* Tim: Once WG forms, we can figure out that process.
* Sam: Any intuition on that Ben?
* Ben: I would assume there would be sensible agreement from everyone.
* Sam: If we start WG, what parts of the spec would be in the WG and what parts in CG?
* Ben: There are some requirements like two implementers, testing, etc.
* Martin: A WG should have consensus. In this case we are chartering deliverables.
* Sam: So spec lives in the WG, and proposals live in CG. What parts of the spec would be in the WG?
* Ben: Not sure at the moment.
* Sam: How do we go about incubation? 
* Erik: Question for the Chromium launch process.
* Tim: merging a couple of trivial Martin PRs. There is a deeper one. I wouldn’t agree with adding SAML specifically.
* Kyle: Do we want to set protocol requirements? Like one OIDC and one SAML?
* Achim: I don’t think there will be specific protocol implementation issues. So we should probably leave it out.
* Kyle: The scope of FedCM features within Chromium in the playground includes authz and additional features like selective disclosure. Do we want to specify how that works: what’s in scope and what is not?
* Tim: I think if mdoc and VC work ends up in the WG we might recharter. For the authz example: that name is not reflective of what it’s doing.
* Kyle: And selective disclosure? I don’t want that to be out of scope. I wonder where we are drawing the line in terms of things considered out of scope and things that are not.
* Achim: We do note some out-of-scope: authentication methods, design of credentials. Everything else is extremely generic.
* Tim: A more aggressive approach would be to explicitly note wallet interaction as out of scope.
* Kyle: We could be back in chartering discussions when trying to add new features. For example, the Chromium #fedcm-authz flag.
* Sam: Our most urgent work is regarding deprecation of third party cookies, and then bounce tracking mitigations. We want to make sure that federation does not break in those cases.
* Tim: So should we talk about third party cookie deprecation?
* Achim: I think no.
* Ben: Probably not. Some issues are addressed in Privacy CG. There were some heuristics talked about in Privacy CG which try to address some of this.
* Johann: For heuristics, we do not want to keep them around forever.
* Ben: Urgency and importance are independent.
* Sam: Would finding a way out of popup be urgent and important?
* Johann: I think these heuristics buy us time.
* Sam: But we want to proactively work on these.
* Ben: I just don’t want the implication to be that we are doing something as the only solution for third party cookie deprecation.
* Sam: Not trying to imply that. Breakage comes before a feature.
* Achim: We put it differently. We want to not break things.
* Ben: This gets to the CG: trying to preserve federated use cases.
* Nicolas: Have we considered the living document process instead of the graduated process?
* Martin: would be supportive of that process. Essentially you don’t work in the do everything to rec and you’re done. Once you get to CR, you create snapshots and then keep working.
* Aram: Specifically language in the charter template that enables that
* Martin: Private Advertising Group is a good [example](https://github.com/patcg/patwg-charter)
* Kyle: I have reservations about the IdentityCredential stuff.  We need to recharter to take that work on.
* Martin: I think that relates to a different question. This is about the working process of things within the group.
* Kyle: OK
* Tim: ok I created an issue for this. Issue 10.
* Martin: Some people said we wanted to absolutely have two of each of the following. My reading of the text is that this is what we aspire to have. I would not want to have an absolute requirement. Not getting to this might be ok. I would suggest we remove the “at least two” clause. We do want people to engage, but should not require this. There is an issue for that.
* Erik: It’s not currently phrased as a requirement. We can clean it up a bit and make it clearer. People might currently read it as required.
* Sam: The browser requirement is a bit harder.
* Erik: It is covered elsewhere.
* John: The browser requirement is mostly to make sure that it is implementable in more than one engine.
* Erik: Right, but covered elsewhere.
* John: But that is a practical thing, not about representation.
* Achim: From a content perspective, the question is whether the language is loose enough.
* Sam: Let’s kickoff a PR.
* Tim: Do we have consensus in the room? (silence = yes?)
* Sam: Kyle, was wondering where does Brave stand? Are you planning to join, and any guidance?
* Kyle: We are supportive. My time is split quite a bit already, so probably won’t be as active as showing up to a call every week. When we see opportunities to make more private defaults, we try to use these, as they align with our user base.
* Achim: Martin, you have an issue 5 about privacy language.
* Martin: The definition of privacy borrows language from other documents. But here I think we need a different definition within that text.
* Tim: I think that makes sense. So I will make these changes. LoginStatus addition will probably be the largest.
* Achim: Ideally we will sign it off on the 25th.

Scribe: Tim Cappalli

### Login Status API

Draft: [https://docs.google.com/document/d/1qZMOTfu22ZC6ZqguDyx83vcUSzeDi_5MIFYS3SBoiUA/edit](https://docs.google.com/document/d/1qZMOTfu22ZC6ZqguDyx83vcUSzeDi_5MIFYS3SBoiUA/edit) 

[Sam]

* Context: FedCM implemented something that looks like Login Status API. Interested in a common notion of what logged in means. Interest in convergence. Challenge so far is that the way Chrome needs to use it right now is different from Safari, regarding the trustworthiness of the bit. Reconciling that is the part we’re discussing
* Proposal: baseline APi that is self-declared, but be deliberate about how it can be expanded. Self-asserted, self-declared login status, which is sufficient for things like FedCM and SAA. If we need more trustworthy signals, we expand it
* Expand navigator interface and also add an HTTP header
* Immediate use for Chrome is in the FedCM API. Some extensions include SAA, extending site data storage, status indicators, and remember me.

[John Wilander]

* Need to have an intermediary namespace under navigator, e.g. `navigator.loginstatus.loggedin`
* Also should talk about expiry due to user inactivity (extension). Don’t have the opportunity to set logged out because the user hasn’t come back.

[Sam] Do you agree generally with the shape?

[JohnW] originally considered username mandatory, but not sure if it makes sense for FedCM. This is login status, not the login itself. 

[Sam] No immediate plans to use username data from LSA in FedCM.

[JohnW] The intent we had originally was for the signal to be trustworthy so you can’t just claim the user is signed in. For the purposes of FedCM, it is ok to be self-declared. It’s ok to call this parameterless.

[cbiesinger] Log In vs Sign In, in many places prefer Sign In

[JohnW] Should be signedin and signedout

[Sam] with sign in vs sign 

[JohnW] preference to Log In

[Martin] same as John. 

[cbiesinger] fine expiration time as well

[Sam] also suggested not hanging this over navigator `navigator.login.setstatus`

[Erik] Can cross-site iframes set the bit?

[cbiesinger] absolutely not

[Erik] Cookies? Is this for the domain or can this be HostOnly, because I know I’m not sharing auth state between two eTLD+1 subdomains (e.g. maps.big-site.example and mail.big-site.example may have a eTLD+1 of big-site.example but not share login state across the two). Site could be doing one or the other.

[JohnW] RE: expiry, this is just the status, not the actual login or logout. 

[Erik] Could be an easy way to shoot yourself in the foot. If we are able to make it more transactional with auth state it would be nice.

[Aram] Is login the right word? Less concern with login.status. Linguistics are confusing.

[JohnW] I did think about this. Login as a noun is what we’re talking about.

[Aram] I can personally parse it, might make sense to check with some other people that do not have english as their primary language

[cbiesinger] don’t have english as my primary language, I don’t have a concern

[Ben] Status as a member, use a setter/getter

[cbiesinger] Two reasons not a good idea. Doesn’t allow reading it. 

Second: may not be able to indicate success or failure (needs to be async)

[cbiesinger] origin specific, not eTLD+1. Different origin could be a different IdP 

[Johann] why does it have to be strings?

[cbiesinger] preference is to be enums instead of booleans these days?

[JohnW] do we have precedent for this? Would like to have functions say what it is

[Johann] allows for extensibility

[JohnW] many cases where are two phases, login and second factor (remember me after first step)

[Martin] suggest that these changes to the API should be made to the HTTP headers as well.

loginStatus is a value set to `logged-in` or `logged-out`. Remove “action=”

[??] This is a response right? Should say that here. 

[Johann] should it be “Set-Login-Status”

[Martin] save 4 characters if we don’t

[JohnW] if we say Set, developers may understand they don’t need to send every time

[Johann] Set-Login?

[Aram] Is it bad to keep marking the user as signed in? One might shard cache based on whether user is logged out.

[mnot] Set-Cookie is cacheable.

[mnot] Set-Login. Don’t need X prefix

[Aram] do we need to change the navigator API if we’re changing headers?

[Martin] still the same (close enough)

[JW] should acknowledge moving forward that using the response header may silently fail

[cbiesinger] developers have a choice to use JS if they care about knowing if it failed

**Extensions**

[Sam]

Caller of SAA would have a parameter that could say reject unless logged in

[Martin] typed RejectUnlessLoggedIn and didn’t like it. How about requireLogin? 

This is reasonably good: just tell me no immediately if not logged in

[JohnW] this particular extension, chrome folks want fairly quickly.

[Johann] sure, but no particular date in mind

[Sam] extending site data storage

[JohnW] FedCM moving first, so lots of adoption with parameterless calls, so probably want to upgrade to newer flows where prompting the user to get that status

[Sam] Status Indicator extension

[JohnW] aware of the pitfall of freshness of avatars and potential for inappropriate images or text

[Sam] each of these would have an equivalent HTTP Header

[Sam] unblocked from what we need short term for FedCM!

[Sam] One last question about the PR that uses Login Status API (IdP Sign In Status API)

[Ben] Think it's ok, but I need to check. Confirm it can’t be read indirectly by the page. Throws an error.

[cbiesinger] If you don’t make the FedCM request because logged out, still want to delay the promise rejection.

[JohnW] loading avatar for freshness could be a side channel

[Sam] where do we go from here process wise John? Repo access? Is writing the spec a next step?

[cbiesinger] immediate future, keep in FedCM spec, then move it out in a few weeks

[Sam] take snapshot and put it in the meeting notes?

[Kyle] Extension for IdP/Browser indicating that the login status is ephemeral? E.g. Off-The-Record mode?

[cbiesinger] making it possible to query that the browser is in incognito mode?

[Kyle] maybe yes, sounds bad. Is it possible for the web page to set that this is a time limited session. For example, link where the link expires in 15 minutes.

[JohnW] ephemeral is not just private browsing, can just be ephemeral in memory. This is only reporting the status to the browser. Site can still log out whenever it wants to. Ephemeral would just be the browser thinks you’re logged out.

Browser just thinks you’re not logged in.

[Kyle] don’t think there’s an issue then

[Sam] markdown file to FedCM repo

[JohnW] we’re going to want to keep some of the language of the existing proposal

[Sam] how about a new repo?

### Web Payments Joint Discussion**

* Conflict with FraudCG - Discussion cancelled

### Other Issues

[Nicolas] Two proposals, would like feedback sooner rather than later

[https://github.com/fedidcg/FedCM/issues/488](https://github.com/fedidcg/FedCM/issues/488)

## Attendee list (please sign yourself in)

* Tim Cappalli (Microsoft Identity, co-chair)
* Achim Schlosser (European netID Foundation, co-chair)
* Johann Hofmann (Google Chrome)
* Kyle Den Hartog (Brave)
* Aram Zucker-Scharff (The Washington Post)
* John Wilander (Apple)
* Pascoe (Apple)
* Benjamin VanderSloot (Mozilla)
* Martin Thomson (Mozilla)
* Erik Anderson (Microsoft Edge)
* Sam Goto (Google Chrome)
* Nicolás Peña Moreno (Google Chrome)
* Christian Biesinger (Google Chrome)
* Ben Wiser (Google Android)
* Chris Fredrickson (Google Chrome)
* Jean-Yves Rossi (Canton)
* Kyra Seevers (Google Chrome)
* Gina Biernack (Google Identity)
* Dirk Belfanz (Google Identity) 
* Harald Alvestrand (Google WebRTC) 


