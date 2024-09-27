# FedID CG/WG TPAC Session, 24 September 2024


**Notes from Monday’s session are available on GitHub: [https://github.com/fedidcg/meetings/blob/main/2024/2024-09-23-TPAC-notes.md](https://github.com/fedidcg/meetings/blob/main/2024/2024-09-23-TPAC-notes.md)** 

## Attendees

* Wendy Seltzer (Tucows, Invited Expert)
* Nicolas Pena Moreno (Google Chrome)
* Zachary Tan (Google Chrome)
* Christian Biesinger (Google Chrome)
* Chris Fredrickson (Google Chrome)
* Heather Flanagan (Spherical Cow Consulting)
* Erica Kovac (Google Chrome)
* Yi Gu (Google Chrome)
* Bert Bos (W3C) – observer
* Laurens Debackere (Digitaal Vlaanderen) \- observer
* [Joel Antoci](mailto:joel.antoci@shopify.com) (Shopify)
* Brian Daugherty (Google Identity)
* [elf Pavlik](https://elf-pavlik.hackers4peace.net) (independent, Solid CG)
* Nithyananthan Poosamani (Samsung)
* Emily Lauber (Microsoft, Identity)
* Bumblefudge (Protocol Labs)
* Sameera Gajjarapu (Microsoft, Identity)
* Zachary Cancio (Google Chrome)  
* Brian Campbell (Ping)   
* Aaron Parecki (Okta)  
* Sam Goto (Google Chrome)  
* Alan Buxey (MyUNiDAYS Ltd.)  
* John Wilander (Apple WebKit)  
* Nick Watson (Google Identity)  
* Christine Runnegar (PING co-chair)

# New Agenda \- 

* 15 min: Administrivia  
  * Scribe volunteer(s)?  
  * Reminders:   
    * To contribute: [Working Group Membership](https://www.w3.org/groups/wg/fedid/)  
      * Visitors still welcome\!  
    * [W3C Code of Conduct](https://www.w3.org/policies/code-of-conduct/)  
  * Introductions (name, role, WG member or FedID-curious)  
  * [Current charter](https://www.w3.org/2024/03/wg-fedid-charter.html) (FYI)(recharter is at the end)  
  * [FedID CG/WG Process Mechanics](https://github.com/w3c-fedid/Administration/blob/main/proposals-CG-WG.md) (FYI)  
* 30 mins: Lightweight FedCM 

  * Lightweight demo with Ben/Johann/Erica

  * [Is there a way to maintain UI hint freshness without falling back to heavyweight FedCM \#40](https://github.com/fedidcg/LightweightFedCM/issues/40)

  * Proposed next steps for this work item

    * Stage 2

    * Draft spec text

* Proposals looking to advance to Stage 2  
  * 30 min: [Button Mode](https://github.com/w3c-fedid/button-mode) – Yi   
    * Issue 442: [A not-yet logged in IDP has no route to success with this flow](https://github.com/w3c-fedid/FedCM/issues/442)   
  * 30 min: [Custom Requests](https://github.com/w3c-fedid/custom-requests) – Christian  
    * Issue 555: [Allow IdPs to continue and finish the request in a popup window](https://github.com/w3c-fedid/FedCM/issues/555)  
    * Issue 556: [Passing arbitrary parameters to the ID assertion endpoint](https://github.com/w3c-fedid/FedCM/issues/556)  
    * Issue 559: [Allow RPs to selectively request attributes of the user’s profile](https://github.com/w3c-fedid/FedCM/issues/559)  
* Normative Specifications: to enter Stage 2, looking for WG consensus that this is a useful direction to pursue as the basis for work  
  * FedCM Proposal looking to advance to Stage 2 (cont’d)  
    * 30 min: [Multi-IdP](https://github.com/w3c-fedid/multi-idp) – Nicolás  
      * Issue 319: [Allow multiple IDPs to be used](https://github.com/w3c-fedid/FedCM/issues/319)  
    * \[reshuffle\]  
    * [10 mins: SAA Auto-grant](https://github.com/explainers-by-googlers/storage-access-for-fedcm?tab=readme-ov-file#example-use-cases) – Chris / Johann / Yi / Ben  
      * Issue 467: [Use cases for Cross-Site Cookie Access through Storage Access API after FedCM grant?](https://github.com/w3c-fedid/FedCM/issues/467)  
  * 15 min: Login Status API  
    * [https://github.com/privacycg/is-logged-in](https://github.com/privacycg/is-logged-in)  
    * [https://github.com/w3c-fedid/login-status](https://github.com/w3c-fedid/login-status)   
  * 30 min: Error API – Nicolás  
    * Issue 488: [Users may be confused after showing intent to sign in but the sign-in is failed](https://github.com/w3c-fedid/FedCM/issues/488)  
  * 10 mins: Heuristics – Nicolás  
    * Issue 517: [Allow user agents to use "Connected Accounts Set" with flexibility](https://github.com/w3c-fedid/FedCM/issues/517)  
* 20 min: [Recharter status](https://www.w3.org/2024/07/wg-fedid-charter.html) \- Responding to the Formal Objection and other feedback  
  * [https://github.com/w3c/charter-drafts/pulls?q=is%3Apr+is%3Aopen+%5Bwg%2Ffedid%5D+](https://github.com/w3c/charter-drafts/pulls?q=is%3Apr+is%3Aopen+%5Bwg%2Ffedid%5D+) 

# Notes

Heather  
Session will be extended until 5pm to make up for the lost session earlier this morning.

Ben  
Lightweight Fedcm ([explainer](https://github.com/fedidcg/LightweightFedCM/blob/main/README.md)) is trying to make FedCM as copy pastable and as easy to deploy as possible while preserving many of its qualities. You can store a credential on the IDP origin and provide a list of things either dynamically or statically then request it from the credential store i.e. WebAuthn, navigator.credentials.get or a URL to navigate to if you don’t have a credential.  
\-Demo- ([demo site)](https://lightweight-fedcm-provider.glitch.me/) ([source](https://glitch.com/~lightweight-fedcm-provider))  
Includes SAA (Storage Access API)  autogrant within invisible iframes

Vitalii  
Do you foresee any options for IDPs to have a say of who we can lose credentials to? Do you provide nonce security?

1. The browser can send a get request to it using CORs  
2. Another way is to provide a static list of origins and the type parameter which Aaron showed yesterday

John (WebKit)  
Is it disclosed to the user that there will be silent SAA?  
I want to bring my identity from this provider to this RP, that is more obvious that the linking of identities.

What is the scope of the storage access, is it on the landing page only?  
You are able to get a silent param with the request access call in the iframe, it simply only removes the UI barrier on the page for the browsing session.

Johann  
We are prototyping this. Under certain circumstances, FedCM also provides storage access.

John  
Some IDPs are also advertising networks so they would be able to use this?

Johann  
That’s why it only lasts for as long as the session lives. Permissions policy is already restrictive, the RP already has to specify the policy and in terms of privacy its the same as just simply post messaging within 1P.

John  
Would that mean FedCM would be incentivized to not call logout?

Ben  
Yes that is true

Nicolas  
Prevent silent access is used to avoid if the user logouts and gets auto re-authned when they didn’t want to be. Question regarding the demo: one row is an apply presumably an account and the other is the origin?

Ben  
It’s an example of one with a hint and one without.

Nicolas  
What does the IDP do when the user signs in with an account without an account hint?

Ben  
It’s up to the IDP, they can redirect the user to a different place.

Sam  
Part of it is you’re allowing the login URL to be something the RP specifies, it can be link decorated so the identities can be joined.

Ben  
Currently you can put whatever you want on the url, I think it’s unreasonable to hold a very high bar for bounce tracking when there is no clear solution on how we can mitigate it.

Johann  
At least for Chrome, we tend to avoid trying to allow it in APIs because if they are used in the APIs then they will never go away.

John  
We need to look into the incentive for never calling logout. We should never assume a pre-existing threat model. If I'm hearing correctly, you are implying silent storage is okay if the RP could otherwise coax the IDP to post message.

Johann  
We’re exactly following the privacy model of FedCM. 

Ben: [https://github.com/fedidcg/LightweightFedCM/issues/40](https://github.com/fedidcg/LightweightFedCM/issues/40)

[Issue 40](https://github.com/fedidcg/LightweightFedCM/issues/40) was something that came up, i.e., gap in lightweight FedCM and regular FedCM in functionality.  
Problem: UI freshness  
Potential solutions: Web Push or using expiration dates

Johann  
Wasn’t there a hybrid version which calls back to the original FedCM? Maybe that’s a compromise where if you cannot use full FedCM, you would have to set expiration dates with lightweight FedCM.

Sam  
Maybe we could hear from Shopify or Google Sign in with how important account freshness is. The first feedback we got for full FedCM when we were debating between the pull and push model was that it was much easier to pull than to push. What’s your target audience, Ben? When we heard from bigger IDPs, full FedCM seemed to be well adoptable.

Ben  
We have to consider smaller IDPs as well.

Johann  
I personally love to rely on just Javascript instead of endpoints.

Vitalii  
Maybe for really small IDPs that don’t care about freshness this could work. For IDPs that care about users and security, you would still end up creating endpoints for “do we trust this RP” and we add two more endpoints and we’re done. This is easier than dealing with service workers and a bunch of client side code.

Erica  
[https://github.com/fedidcg/LightweightFedCM/issues/42\#issuecomment-2350051647](https://github.com/fedidcg/LightweightFedCM/issues/42#issuecomment-2350051647)  
If we can reduce the number of endpoints that IDPs need to implement, it would help; i.e., if there isn’t a specified accounts endpoint, we would make do without it by checking for stored accounts.

Ben  
Next for lightweight FedCM: Iterate checklist for the next stage, make requests, and write spec text
# Active Mode 

30 min: [Button Mode](https://github.com/w3c-fedid/button-mode) – Yi, (now known as Active Mode)

* Issue 442: [A not-yet logged in IDP has no route to success with this flow](https://github.com/w3c-fedid/FedCM/issues/442) 

Yi  
Today’s FedCM UI only works when you are signed into IDP, when you are not signed in, no UI is shown. That’s why we’re proposing this mode API. With some user activation, we capture user intent better and we know that the user wants to sign in to this RP with this IDP.

\-Demo-  
“Active” mode implies we are actively trying to get the user to sign-in if they aren’t already signed in.  
“Passive” mode implies we are more passive in trying to get the user to sign-in if they aren’t signed in, this is the default.

Proposing to move this mode API proposal to stage 2\.

Joel  
We like this proposal because it gives the user a chance to sign-in. Is there enough of a signal that the user wants to sign in to this RP once the user clicks on the button? Can we skip the dialog?

Yi  
At this point, it is not guaranteed. It’s a strong signal that the user wants to sign in, but from a privacy perspective, we need to ask for the user’s permission.

Elf  
How does active mode work with user-registered IDPs?

Yi  
With the IDP registration API today, we only support it with passive mode. I don’t see any reason why we shouldn’t support active mode with IDP registration API.

Heather  
Any volunteers to review PRs? \[crickets\] We’ll ask on-list.

Wendy  
Any objections? Hearing none in the room. (We’ll also ask on-list) Any issues? Please file them in the active mode [repo](https://github.com/w3c-fedid/active-mode) if needed.

* 30 min: [Custom Requests](https://github.com/w3c-fedid/custom-requests) – Christian  
  * Issue 555: [Allow IdPs to continue and finish the request in a popup window](https://github.com/w3c-fedid/FedCM/issues/555)  
  * Issue 556: [Passing arbitrary parameters to the ID assertion endpoint](https://github.com/w3c-fedid/FedCM/issues/556)  
  * Issue 559: [Allow RPs to selectively request attributes of the user’s profile](https://github.com/w3c-fedid/FedCM/issues/559)

# Continuation API

Christian  
Continuation API bundle demo (Continuation API, Params API, Fields API)

Proposing to move this mode API proposal to stage 2\.

John W  
Continuation pop-up, is that browser UI or page UI? We generally try to never let webpages put text in the browser UI.

Christian  
It’s a regular pop-up, the same that you get with a window.open. It is a URL specified for the IDP.

John  
Our experience is that some IDPs are reluctant to disclose how data is shared. How do you view that, is that a risk?

Christian  
It’s a possibility. The IDP can only share what they already have. There’s nothing that stops the IDP from sharing anything they want even without the API.

John  
Sounds like a not great way to design if we want to improve things. Proposal to show at least one thing in browser UI.

Christian  
IDPs like flexibility. The pop-up is not only to show the disclosure text; they might also get you to verify your email, phone number, etc. There’s also asking for access to email, drive, etc.

Vitalii  
We are also an OAuth provider which allows third parties to call our API. There are GDPRs in the world that want us to write in a very specific language.

John  
I can see the benefit of showing the pop-up to show extra context, but being able to suppress information in the browser UI by not showing the dialog is an issue to me.

Christian  
We do let the IDP know what we show in the dialog, and they can decide whether they want to add to it.

Ben  
I have a question/concern with the accuracy of the information being shown in the dialog: say if it says name, email, is that all that is being shared to the IDP? The consent dialog is misleading to users because there’s a high-entropy identifier being shared to IDP

Sam  
I believe “Sign in with rp.com with idp.com” is inclusive of that contract that they are willing to provide their unique identifier but this language is not easy to put on the dialog.

Vitalii  
Email is indeed a high-entropy identifier and it is listed.

Ben  
This is exactly part of the challenge of FedCM as a whole.

Heather  
I’m hearing some concerns that may or may not be browser UI specific, so should we still move this into stage 2? Do we want to continue iterating or is there enough here?

Ben  
I don’t see anything that stops it from moving to stage 2\.

Heather  
No objections to moving this to stage 2\.

# Multiple Config URLs

Christian  
\[ Demo of multiple config URLs \]  
Proposing to move this mode API proposal to stage 2\.

Johann  
How do you know which config URL to use?

Christian  
RP specifies the config URL. This proposal checks that the account's endpoint matches the config URL.

# Account Labels 

Christian  
\[ Demo of account labels \]  
Proposing to move this mode API proposal to stage 2\.

Johann  
An RP can specify the label so is there passing of data before the user consents?

Christian  
No, this is on the client side and doesn’t get passed to the server

Johann  
If an RP can specify config URLs is there passing of data before the user consents?

Christian  
It can only affect the uncredentialed requests.

Johann  
Uncredentialed requests include information about the RP correct?

Christian  
One of them does, yes.

Wendy: we went over Account Labels and configURLs to advance to Stage 2

Ben: Stage 2 sounds good to me, but the email out to have others review would be useful

Wendy: sounds good to me, we’ll provisionally send the email and ask the people in the list to review

# Multi IdP To Stage 2

- Nicolas: FedCM currently only allows one IdP to be used at a time, it would be useful to show more than one at a time if they support them. Also useful for the IdP Registration API.  
- Nicolas: We are going to start with the simple case, allowing a simple “get” call, to use them combined in the dialog. The proposal is to fetch them all at the same time, wait for the result … and build the dialog.  
- Nicolas: In the Multi-IdP scenario, we’re going to have to deal with the mismatch UI.  
- Nicolas: We have been working on this API for a while, so wanted to propose to stage 2\.  
- Nicolas: Current status quo, nascar flag, with FedCM multiple IdPs being used in the same account chooser.   
- Nicolas: gmx.de and web.de, large email providers in germany, participating in the origin trial  
- Nicolas: browser implementation choices, prioritizing returning accounts at the top … if you have a single returning account, we just show that returning account first because that’s likely the one that users want to use … helps with spam …  
- Nicolas: In terms of the idp mismatch scenario, for privacy reasons, we have to show the idp login url, we show it alongside the accounts that we fetch from other IdPs.  
- Nicolas: The proposal is actually quite simple, we now support a providers array of arbitrary size, and we have the IdentityCredential.configURL that helps the RP figure out how to interpret the response, since it can come from any one of the IdPs.  
- Nicolas: We have in the explainer a whole set of different alternatives … we’ve been devtrialing for a while … and now an origin trial with a big partner that is running in production ….  
- Gioele: A badly configured IdP preventing the FedCM to show at all, is there a timeout to solve this problem? This can be a stage 2 conversation.  
-  Nicolas: Known issue. The current implementation doesn’t have a timeout, but should we include that? Don’t know whether the browser would pick a timeout   
- Gioele:   
- Nicolas: another option is considering dynamic UI …. A general case of aggregating multiple get calls…. Where essentially independent IdPs … to be able to support … for now, my best idea is to wait until all of the IdPs resolve, or update the UIs as we get the data from IdPs …  
- Elf: does the API also work with the IdP Registration  
- Nicolas: this is a prerequisite to the IdP Registration API, yes, it should enable the IdP Registration …   
- Wendy: not seeing any other hands raised  
- Wendy: Do we have any objection to moving this proposal forward to stage 2?  
- Wendy: not hearing any.  
- Wendy: we’ll be asking for volunteers for PR reviewers … 

\[agenda-juggling\]  
Wendy: let’s prioritize the issues that the folks in the room need to discuss

# SAA Auto-grant 

- Chris: as we were discussing earlier there is the SAA auto grant, this has now been implemented in chrome and is in origin trials …   
- Chris: there is a repository for the explainer for this … [https://github.com/explainers-by-googlers/storage-access-for-fedcm](https://github.com/explainers-by-googlers/storage-access-for-fedcm)   
- Johann: it is a trust decision to the SAA to use the FedCM signal   
- John Wilander: are you suggesting that this is mandatory? Or is this optional? Can the browser limit scope or time: Is it for the full browser or only the page where it was initiated by the IDP  
- Johann: you have a FedCM grant, at the point where we look at the SAA algorithm, and we go through all the steps, there is a new line now that says, in addition to the SAA permission check, if there   
- Depends on the browser how they set the FedCM permission. Could be used by calling navigator.credentials.get. Whatever scope you give the FedCM grant, that’s the scope this API uses.   
- John: Why is this requested? What additional use cases are supported?   
- Johann: FedCM gives you a token. A lot of people do session management with cookies.   
- John: It’s the idP you’re talking about  
- Johann: in this case. There are [two examples in the explainer](https://github.com/explainers-by-googlers/storage-access-for-fedcm?tab=readme-ov-file#example-use-cases). SAML redirects. IDP managing state in an iframe.    
- John: I’ll have to read up on it. How much are you relying on?  
- Johann: we’re matching the FedCM grant. If there’s a FedCM connection that hasn’t been canceled.   
- John: something we have to identify in the work on login status API. If you rely on that as trustworthy signal, have to make sure a logout is a logout, so as not to incentivize sites to not logout  
- Ben: good insight to think about in terms of Lightweight  
- John: some people have suggested browser UI to show “currently logged in” but real estate is limited. I’m going to havre to read up on the explainer

# LoginStatus  

John: as editor in PrivacyCG, see three goals. 1, move CG spec, repo, to WG. As editor, I favor that. Then transition to a joint understanding of how it should work with the document Sam has led. Assume we should do that in pieces, motivation, shape of API, etc. 3\. Have some feedback from me that we don’t really like the strings status as in Chrome, but would prefer functions.  So everyone knows, for us, the login status has much broader use than FedCM. Experimentational implementation connected to Webauthn, trustworthy signal  
Christian: What's your proposal regarding strings vs functions?  
John: functions setLoggedIn(), setLoggedOut(). Open to TAG feedback  
Sam: Chrome uses a webIDL enum. To be concrete… At the last TPAC, we had a 2-day meeting, left with an understanding of what we wanted as API shape.  
John: I don’t recall the conclusion that we were happy with it; didn’t want to stop you from moving if you needed to. Now we have an opportunity to make a much nicer API. You can keep your implementation and forward it.   
Sam: We don’t want to maintain two branches. Would be a backwards-incompatible change.   
Sam: 2 days worth of meetings, think Martin was there  
Johann: I was there  
Sam: The notes record we talked about methods v strings.   
John: it differed significantly from the original shape of the API.   
Johann: I hear you (John) saying you prefer a different API shape  
John: and I’m open to joint conclusion if it’s for the current shape  
Johann: Can you walk us through considerations of how it helps the browser to help the user? What’s the developer story?  
John: We think there’s a gap in the web platform, that the browser doesn't know when the user is logged in or logged out. That has never been standardized. We’ve made progress on AuthN, with webAuthn transaction, but not state. Even more important is to standardize logging out. Would be a great thing to add to the web platform, filling gaps. Wan this to be a trust signal, so we can make decisions for security and privacy based on that signal, e.g., probably more ok to allow access to powerful APIs with fingerprinting risk if the user is logged in. That could help resolve several hard standards conversations. Be more relaxed on storage lifetime when user is logged in. Keep data where you’re logged in, clean up data when you’re not. Those are my major drivers.  
Johann: What’s the developer API story? How does dev use this API in your view? Have you made progress on how the trust signal would be recognized?  
John: we detect there’s a browser-mediated login, only in a certain time after that, allow setting of logged-in status. That’s a gate. Challenges, there are login methods that aren’t browser mediated, e.g., click email link, need affordances for that. E.g., the site says “I use a different method” and the browser exposes to the user that site says they’re logged in. Second, what happens to sites that are logged in at the time of switch? Then, federated case. How do you transfer the trustworthy signal, from logged in to federation to new site. Logout, how do we ensure sites don’t keep logged-in status when the user has logged out or timed out, to keep privileged access. 

Johann: to the first question, sounds like dev would call API, promise resolved or not resolved based on the signal. Is there any point in this being an API, then?   
John: People confuse authentication with being logged in. Seeing AuthN doesn’t mean user is logged in. it could have failed. Having a confirmation step, where the site says, user is logged in, is important.  
Johann: it’s not visible to the user. So there’s no incentive for them to help you.   
John: there will be sites that don’t care, that’s fine. They don’t need to use it.  
Johann: you’re risking that login fails and site leaves the logged-in set. The heuristics are hard to get right.  
John: other benefits we talked about in PrivacyCG. Maybe there’s a status indicator sites want. Browser affordances to help users know where they’re logged in (a browser feature not a web feature)  
Johann: it’s hard for me to figure out how we’d do this. Would be great to get an end-to-end version of what we should implement, with the minimal viable product.   
Sam: What I heard from John was you wanted 3 things: and you said spec \- there’s no spec, just an explainer right now. You’d like to see repo in the PrivacyCG move to FedID WG to preserve history of issues. Works for me. Second, you’d like to see explainer we collectively wrote from last TPAC incrementally merged to the repo. \[John yup\] And you’d like to see the API revisited.   
We left the   
Heather: I wasn’t at last TPAC. speaking as chair, I have no meeting notes w sufficient detail to know what was presented. Proposal to bring over the repo and add the explainer incrementally doesn’t sound bad  
Sam: I wouldn’t know how to move the explainer incrementally, as I thought the whole text was agreed to. If you have proposal to break down into multiple PRs, we’d welcome that. Are you abe to commit to participate as an editor?  
John: yes.   
Heather: Apple is now a member of the WG  
Sam: we have text in the repo as First Public Working Draft. Can you join weekly editor meetings to get this resolved? Current API is shipped in chrome, has small number of users, wouldn’t change lightly  
John: always good to have a path to standardization with multiple implementations  
Ben: I don’t have distinct recollections of co-writing from last TPAC either. … current discussion doesn’t reflect that there was deep consensus then, and people can change their minds as they learn new things. Discussion of making the signal trustworthy. Let’s not get hung up on something said in a CG call a year ago.   
Heather: I’m hearing commitment to work on it, good news. A process note, if you have editors’ calls, please take notes and come back to the group so we can see what’s recorded in issues  
Ben: I’m surprised ot see myself as a suggested editor  
Sam: would you like to be?  
Ben: give me some time  
John: it would be great to get more engine diversity. We had previously worked with Melanie Richards  
Johann: I don’t really see practical next steps, still.    
Sam: we talked about how you trusted signals, beyond self-asserted. There’s a spectrum. It wasn’t clear to us how higher trust would come. Logout doesn’t have an equivalent in other APIs. Somewhere in the middle, login status indicators.   
Ben: recall discussion of self-asserted version, and higher… A year of experience might lend us some fresh eyes.   
Sam: our timeline came from a concrete case where we could use login status API.   
Ben: Heard a prerequisite for some FedCM to ship, December.   
Sam: we could have implemented something FedCM-specific, but took extra effort to make distinct.   
Heather: However we got to the text in FedCM, we now have some interesting running code to inform our discussion. Apple has some use cases. W e have more info than we had a year ago.  
Johann: self-asserted and browser-verified are fundamentally different that we need to have a better idea of what other thing we’re trying to build here. How as browsers do we assert “login happened”; what does the API look like? Finally why are we doing this? Don’t think Firefox or Chrome have plans to do those other things. There’s a lot of work to commit to if we don’t have those uses  
Sam: I’d also be ok making this FedCM-specific login status  
Johann: that’s a good subset. I’d still like to explore further  
John: I’m hearing that you want to discuss more before you have a work item or move the repo?  
Johann: This seems like a hard problem, a lot of time to invest. What are the concrete benefits of having the signal?  
Heather: I don’t want to have happen, move it and then the WG kills it without the PrivacyCG convo. One more dedicated conversation …  
Brian: an observation, the slightly different, it’s used only in the FedCM context to show what   
Sam: it’s a signal to FedCM. FedCM takes login status as signal to what to put in its account chooser. If it knows you’re logged in, logged out in a self-asserted way  
Johann: what’s being proposed, use that signal to grant privileges. So think about how trustworthy that signal can be made  
Brian: sounds to me as though it has some small utility to FedCM in small way that may be obsoleted by IdP registration function, where IdP registration would enable the account list to be populated.   
Sam: IdP registration API prompts the user for permission; whereas login status is self=asserted and doesn’t prompt the user  
Johann: the prompt is what John wants, yes?  
John: I’m fine with the engine capturing different trustworthy levels, self-asserted with no trust and higher levels. That would be up to us to work out  
Johann: if login status API si being called, youd have weak signal. If user calls IDP registration, strong signal  
John: exactly   
Heather: elf notes in chat that use cases and requirements could help clarify the problem space.   
Sam: can we try to find some resolution in the hallway? Chrome doesn’t have intuition for using self-asserted signal for anything other than FedCM. Wondering if we should be more FedCM-specific, expose a static method…  
Johann: I want to support this API long-term, want to hear more from webkit team in drawing it out more completely  
John: Maybe I’m surprised other browsers aren’t looking to use a logged-in signal, e.g. fullscreen, other features.   
Ben: As I have, which is why I think it does have merit. Don’t know where it falls on priority list, but think there’s clear utility. Deciding how it get set is the hard part. E.g. notification  
John: for me, it feels natural to add infrastructure like this and innovate on top  
Sam: Chrome uses the bit  
Johann: if you have proposal, don’t partition sites that want to show notifications based on this infrastructure, that’s a concrete change we can consider? But gating privilege generally is big change.   
Sam: where do we go from here?  
Johann: if we had a clear place to use it, we wouldn’t stand in the way.   
Sam: I hear Johann suggesting we rename what we have to idp-login-status to make it FedCM-specific, that would be backwards compatible, then a fedcm-specific signal. If we learn it would be useful for other things, we could then expand  
Johann: that could work  
Heather: our charter says “a separate deliverable to be used in FedCM”  
John: if that’s the direction, then a well-scoped to federated logins and unfortunate to have two similar APIs  
Johann: doesn’t seem as though we’re all talking about the same thing  
Ben: I was just rereading the notes from the last breakout session. Last comments seem to hold. I think it’s a shame that they would be separate. Privileged login status could be informed by the context in which the call was made and use that context to inform the API. The details of the privilege aspects of the API would be in PrivacyCG. Get an early TAG review on the name if we sort that out.

Heather: I’m hearing next steps, not move the repo at this point in time. FedCM has login status, and we’ve got some issues to put into the repo. Not concluding against moving the repo in the future if it comes to the point that we need higher-trust signal.   
Sam: John, are you comfortable to keep 2 repos?  
John: and you maintain the FedCM one?  
\[discussion of naming, to be continued\]

Chairs: thank you to participants, scribes. Go to breakouts tomorrow  
\[meeting adjourned\]
