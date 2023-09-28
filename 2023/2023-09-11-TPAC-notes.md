# FedID CG notes, 11 September 2023 (TPAC)
Scribe: Rick Byers

## Agenda

* Welcome & Administrivia (11:30-11:45)
  * Scribe volunteer(s)?
  * Reminders: 
     * [Community Group Membership](https://www.w3.org/community/fed-id/)
     * [W3C Code of Ethics and Professional Conduct](https://www.w3.org/Consortium/cepc/)

* FedCM demo and browser status (11:45-12:30)
  * Chrome
  * Firefox

*  Lightweight browser interaction vs heavier engagement (12:30-13:00)
   * Firefox proposal (Ben)
   * What’s the relationship between FedCM and the SAA? (Johann)

## Notes

### Demos

* Nicolás Peña Moreno - Chrome
    * [FedCM Demos](https://docs.google.com/document/d/1bh3eir1_1ZpP4rBmzmlYPi4p91FaXexbXrsfX5If1XQ/edit?resourcekey=0-l2K3AuFL5EFakfQK9TCuOw)
    * Sam: we brought demos for things we've already launched, things that we're working on and things that are more inspirational
    * Nicolás: Since last TPAC we hadn't shipped FedCM yet. Now we have. First demo is baseline FedCM API. 
        * Note that you have to be logged into IDP first before using FedCM.
        * Demo page has fake sign into IDP website to setup different types of cookies
        * See in top right corner - browser window saying "sign in to [RP eTLD+1] using [IDP eTLD+1]", with account chooser showing name, profile picture and name
        * When selecting one, get a confirmation dialog - "Continue as Elisa"
        * Can see that RP received token from IDP via FedCM API
        * That's the basics - what FedCM 
        * RByers: what's deployment status?
        * Nicolas: main partner is Google Identity services, have been experimenting with the API on a small percentage of their users. We don't see a massive amount of usage. At 0.004% of Chrome page loads, a small fraction of Google Identity Services at the moment. We do anticipate that before Chrome phases out 3PCs, we anticipate usage to grow significantly because Google One Tap widget will be replaced entirely with using this API. We will see a lot of API usage from that partner alone. We've also been working with other partners - Times of India, some others at earlier stage talks but not much traffic. We're happy to chat for any other use cases.
        * Tomas - noticed there is no button you have to click for FedCM?
        * Nicolas: Correct. Mozilla may not agree, might require user gesture in some cases. But we're trying to address some use cases that don't have a user gesture so our API doesn't require a user gesture. But there will be future enhancements ("button flow") that will require a user gesture. Right now if you decline the FedCM prompt it puts it on "cooldown" so that we automatically decline - won't show in all cases website tries to show.
        * Tomas - technically could have a user gesture?
        * Nicolas: Correct. But could be tricky for an RP because at the moment FedCM isn't guaranteed to be shown
        * Sameer: Is autofill a user gesture?
        * STephen: Triggering of autofill is a user gesture, but completing autofill isn't
        * Nick Doty: what the user cases for not having a user gesture? Are they cases a user wants or just when a site wants to harass a user?
        * Nicolas: Certainly where the website wants the user to be logged in in order to use the website. So makes sense to show the prompt when the page loads. Lots of websites currently show the google one tap widget on page load instead of waiting for a user signal. Generally a website that only works well when a user is logged in. In that scenario it makes sense to show the prompt without a user gesture? But it's a valid question - should the web platform allow a login window to be shown without a user gesture? Mozilla's feedback is maybe not. So we have differentiating opinion on this between Chrome / Firefox but we want to create a standard that works across all browsers but we
        * Sam: intuition is that browser can control the volume of the disruption so that it's proportional to the user intent. So when there is a user gesture we can construct UX that is more modal like a dialog, but without that the browser could construct uxes that are eg. less blocking, smaller. Looked at using omnibox, url bar, or even lower visibility things. User Agent will make a judgment on how to make volume proportional to the user intent
        * ? What do you mean proportional to the user intent?
        * Sam: We have the notion of a user gesture today as a signal of user intent. So we design APIs for how to behave with or without user interaction. Intuition is that it's not appropriate to show a modal dialog without user interaction. That's what we mean by intent - but it's an approximation.
        * Kyle: Elsewhere I've seen wallet initiated flows. WDYT about a browser-initiated flow where it flips the pattern to the user - configured like how they configure permissions (ask to be prompted every time, or initiate from browser, or webpage could prompt as fallback).
        * Nicolas: Yes. This is similar to what Mozilla has requested - Sign-in status API. If I understand correctly, want the user to indicate that they want to use a particular IDP before RP can show. We're trying to incorporate this into the spec so if that's what a UA wants to do, it can. User may or may not be logged in. If not, IDP can provide sign-in URL so user is directed to that URL to sign-in. Once the user signs into IDP top-level site, then show account chooser. 
        * Kyle: Have you considered a promise-based structure where the promise doesn’t resolve until a user addresses the prompt (or if it were pre-configured, etc.).
        *  Christian: My understanding is that the current API already allows for that. Think it's already possible with the current API.
        * Kyle: Rather than add an additional API for the flow, can we bolt it onto the current API?
        * Nicolas: Yes, it will be incorporated into the n.c.get call, so yes built into the FedCM API flow. 
        * Tim: There is a discussion on this login status on Thursday at 9:35 (?)
        * Ben: On interop and user interaction: agree we want a compatible specification. Just a question of how much we want to specify. We could have a very compatible spec that that anything goes. I think that whether a user gesture is required for the API to work should be something we specify. Does the developer need to have a click in order to call the API and have it work in the way they expect seems like a good groundwork for developer expectation
        * Nicolas: I think you're right. It's currently specified to not require a user gesture, and we do want some flows to be spec'd to require it like the button flow. Maybe we don't agree on the baseline of not requiring it for some flow, but agree that if UAs behave differently without a gesture it'll be an interop problem
        * Ben: Other than the button flow, the approximation of google one tap - having it come up without user interaction is there any indication to the user that it's not a traditional one-tap not bound to an iframe?
        * Christian: Short answer is no. Technically you can tell because we show a domain name. Why do you ask?
        * Nicolas: There's nothing indicating it's browser UI - we want it to be the website's responsibility to decide if UI should be shown, don't want to suggest that Chrome is encouraging the user to sign in. It is Chrome UI but it looks similar to current google one tap UI
        * Ben: To take current experience that's very common (one tap on page), transforming into browser UI is debatable
        * Martin: Will be perceived as being creepy by some people
        * Sam: If people consider it creepy we can decrease the volume eg. by showing smaller / in a different place
    * Achim: Ok let's leave google team to demo other scenarios. We'll have more time tomorrow.
    * Nicolas: RP context feature - RP gives browser context on intent. default is sign in, but can choose sign up, continue, use
        * In Chrome case we modify the title of the prompt.
        * Flow is the same
        * Sam: We think this is useful in scenarios like twitter blue where you're asking 
        * ?: Are you saying it's customizable?
        * Sam: Not a string, 4 choices today but we can add more
        * Tomas: Just changes visual?
        * Nicolas: Yes, good point - just visual
    * Nicolas: Next feature is login hint
        * Remember I had two accounts
        * Demo: typing in e-mail address as hint
        * In this case UI shows only the account that was hinted with "continue"
        * Useful in scenarios where the RP already knows the account the user used, or the user typed in some information already
    * Thomas: this is only a change to the UI?
        * Nicolas: Sort of - a change to the list of accounts in the UI
        * Gerhardt: And if two matches?
        * Nicholas: I won't explain that yet - too early for that demo. But it's a failure.
    * Dom: as a user, can you get stuck if the web site picked the wrong account for that hint?
        * Nicolas: separate feature gated by user gesture where the user showed some clear intent to use a specific IDP, we can show UI to sign into IDP
    * Gerhardt: we've got a lot of questions because we have similar problems in payments UI flow. One of the problem we have is that when SPC fails we can't know why. In this API can we know why it failed?
        * Nicolas: In general you know there's a failure but it may be delayed - we may not tell you right away for privacy reasons. For example, if the user taps on the x to close the dialog, RP is immediately notified. But there are other cases where it would be delayed. For example now it's in cool down after clicking x, if I refresh and reject we add a random delay and we don't tell the RP the reason
        * Christian: we want to make this all indistinguishable
        * Sam: we would like to hear your requirements. We're operating within some privacy constraints
        * Tim: interesting from a consistency perspective eg. WebAuthn has only one generic error
    * Tomas: Hard to know what to do next when there's a delay, what should we offer next?
        * Christian: Can you say what you'd want to do in that fallback case?
        * Tomas: we'd offer some other sign-in method
        * Nicolas: good question, unclear if it's acceptable to not delay when there's a user gesture. User gestures are easy to get. Need to learn more about use case
        * Christian: The answer that fits with current FedCM might be multi IDP support, what we have behind a flag
        * Sam: Maybe interaction with wallets, which we have a demo for too.
        * ?: And breakout session on Wednesday on wallets
    * Nicolas: iframe support demo
        * Initially FedCM can only be called from the top level. To call from an iframe, need to use permission policy to allow iframe to use it.
        * Prompt will show only the top level site because users don't understand iframe origins. Want to show domain that matches the omnibox. Iframe is performing federated login on behalf of top-level
    * Nicolas: mediation demo
        * Optional: logs me in right away because I've already logged into this site before. Just re-uses the same account as previously
        * Required: show the account picker regardless of whether I've signed in before
        * Silent: never see account chooser. Failed because we only allow it every so often. 
        * This follows mediation in credential management
        * ?: What happens if you try after the 10 minute window?
        * Nicolas: It'll show the verify window, assuming I've only used one account before
    * Nicolas: User info - let's IDP personalize sign-in buttons
        * IDP iframe can show an image from the account I picked before. Let's IDP customize UI for returning accounts. Also requires a permission policy because it's inside an IDP iframe.
        * Gerhard: for completeness if user interacts with a personalized button it would trigger classic OAuth flow, right?
        * Nicolas: Right it could
    * Nicolas: That is all the things we've shipped - in Chrome stable today. Do we have time for more demos?
    * Tim: let's come back if we have time
* Ben from Mozilla - will talk about what we've shipped
    * We've only shipped to our nightly / pre-release. We only have the baseline with a few exceptions.
    * We have some differences in our UI. One additional UI element which is a prompt saying "Is it OK if this identity provider uses this API?". Otherwise we have a timing attack which leaks the IDP to the RP which we don't find acceptable. We also have the user interaction requirement. 
    * I say baseline-ish and I'm not demoing because ours doesn't work with the FedCM demo site. The way the spec is currently written is incompatible with the fetch spec. Firefox implementation won't let me do that.
    * Christian: What does fetch spec not allow?
    * Ben: Under no cors request sending an origin header is weird. Honestly long enough that I've forgotten
    * Christian: If you follow the step you find you can do it if the client sets the header manually.
    * Ben: we can get in the weeds on the fetch spec offline, but I believe it's either not OK fetch spec authors would fix that. We have a pending PR on fetch to add a new fetch mode, but it's been quiet and not a high priority
    * Ben: Believe that's about where Mozilla is at
    * Sam: these feel to me like fairly reconcilable differences. Do you think we can get to the point this TPAC where we can reconcile?
    * Ben: For timing attack and user gesture
    * Sam: would like to write the spec such that both implementations are valid according to the spec even if they differ in terms of tolerance for timing attack?
    * Ben: yes we can talk about it
* Kyle: Update on Brave implementation
    * It's currently disabled in Brave, usually our default pattern when a new API is coming in chromium,
    * We're looking at modifying the UI - discussion about whether it should be in the web page itself? We want to move it to site settings permissions. That falls in line with the idea of logging in through browser-prompted UI without taking up additional space within omnibox etc. But under the hood our intention is to just run the Chrome implementation. We might disable some things, but more discussion needs to happen eg. if we want to use verifiable credentials
* Tim: Let's do your wallet demo since finance folks are here
* Gerhardt: we have another joint session on Thursday
* Sam: we scheduled a good amount of time later in the week to discuss wallets because it's fairly early. 
    * [Video of Android]
    * Fake website calling a JS API under development (fake API calls) which looks into operating system's credential store
    * Out of band, wallet have registered with the OS which credentials they have.
    * Shows prototype Android UI that lets you select credentials 
    * Fairly explorational and early, way more questions than answers. Lots of consequences. Very early.
    * Rick: key thing to note is that this is happening with or without browsers being involved. eIDAS 
    * 
* Sam: if anyone wants to see any of this in practice, I have it on my phone - come find me
    * Nick Doty: PING will be discussing some of the common privacy and free expression concerns - for some of us it has fairly terrifying consequences, will need to be seriously addressed.
    * Tim: tomorrow at 5:00
* Nicolas: tomorrow will demo IDP sign-in status API, error UI, hosted domains, revocation, authZ API, multi-IDP API


### Lightweight browser interaction vs heavier engagement



* Ben presenting "Top-Level Storage Access API extension" \
https://github.com/bvandersloot-mozilla/top-level-storage-access
    * There are a few things about FedCM that are heavier weight. Biggest thing we've heard is that requires shipping custom infrastructure for FedCM - HTTP endpoints. Is there a way that we could do this which doesn't have this extra infrastructure
    * One thing that isn't being discussed elsewhere is a very lightweight credential. Credential API spec has a federated credential that is largely useless for this purpose - doesn't actually work well cross-origins. Maybe we could flush that out and make it useful? JS could message pass through CM
    * More attention being paid to roughly the same extension to the storage access API. Not just to iframes with user interaction but also to top-level resources within a document.
    * Top-level storage access API - some sort of request to get storage access to an origin, but for that to work the origin needs to have signed up already to get storage access.
    * The key constraints is that the user must have signed intp IDP
    * Tomorrow at 9:30 in privacy CG a lot of this will be discussed. 
    * Didn't want to take too much time here. Does something like this seem reasonable within the context of FedID CG. You get cookie access within the context of a prior interaction in a JS call.
    * Archim: Discussed previously. RSAFor can do it because embedding site is clear. Would it be the same prompt as generic RSA or notion of being related to login?
        * Ben: idea is that it would be the same - one permission prompt. There's a related general extension push for UI hints for storage access API. Some sort of context for who you are on the site that you're sharing. Some discussion of how much it ties into the UI of FedCM. Key difference is not multiple accounts, potentially just a picture and some identifier of choice. Maybe we could do further things like context that's useful but not necessarily trusted. Tension here around what do you allow website, especially 3P, to insert into browser UI. It's hard, but we'd really like to provide more access in storage access prompts generally
    * Nick doty: I'm not sure I'm following 2 parts. Seems like you're suggesting it would be simpler. But you still require someone to call the JS Call, that seems harder than FedCM infrastructure?
        * Ben: Yes. Also timing attack that's inherent to the space. Ideal is that there's permis storage access argument that is stored which says which sites can request me. One way is a list, or allow all, or a dynamic endpoint that would be hit through a CORS request which might require some sort of dialog to make it work which 
        * Johann: an improvement on forward declared. Pretty good proposal, but mandatory step to open 3P in popup or redirect giving user something to click. Here improvement is that any point in the past IDP can say it's OK for users to get prompts to use this
        * Nick: in terms of adoption they still - why tell them they have to call navigator.* vs. setting up an endpoint?
        * Tim: it's not easy to setup such infrastructure at MS-scale of billions.
    * Nick Doty: Seems like the advantage of FedCM is that it's moving to a purpose-specific API that user's can understand - log in to this website with this website, but it seems you're trying to remove that. Just generic "access to cookies"
        * Ben: Yes, my view of this being a more lightweight solution that's not login specific. The key is to allow the user to provide context of what they're doing with better wording / orientation of that prompt. Rather than scary "you're being tracked". Some idea of "linking this identity to this page" in a way that's more intelligible to the user. I think there is a challenge here. Downside is that if you get a FedCM grant, you can effectively functionally the same as a storage access grant from a privacy perspective.
        * Nick: But the user is intending to do something that they can comprehend. 
        * Ben: This is what we want to address in storage access API with UI hints.
    * Erik: Could be any one of 6 identities if I had 6 user accounts
    * Johann: multi-identity is definitely a challenge there
    * Tim: From my perspective we don't want the generic language of RSA - we tried it and it was bad. 
    * Sam: I don't understand enough, would like to talk more about the tradeoffs. Sees like SA is easy to use but poor UI so we can try to make UI better. FedCM tradeoff is different, harder to deploy but better UI. Conflict with each other, tradeoff.
    * Johann: important to have both. FedCM is fine for that use case, but we might be interested in developing something like this for a more general privacy use case that's not solved by anything today. So we might do this anyway, but want to talk through FedID use cases too.
    * Sam: That separation I understand and support. When it's 
    * Johann: I wanted to make sure we don't discourage FedCM usage when it's the right thing. A gray line there - what is federated login exactly. 
    * Ben: Ditto. Both can exist
    * Erik: when you talk about different ux. What's the chance of the threat model that makes us more comfortable in having the UI be less scary?
        * Ben: There is this prior interaction as a 1P potentially with some indication of what happened and how long. Having that as opposed to current rSA prompt which is very appropriate to rouge 3P. Current language is IMHO out of date relative to improvements we've made in the last few months to the spec to say that it's interactive frames only.
        * Ben: nothing to do with RSAFrom, more of a harm reduction - preventing reputational damage. Argument of which sites you permit. More important piece is top-level interactive nav at some point in the last. 
        * ? Is that a requirement for FedCM to work?
        * Sam: user activation requirement for IDP sign-in
        * Ben: rough proposal that's very negotiable. Lots to discuss
    * Sam: mentioned getting user accounts as hints, Would that be through login status API?
        * Ben: would be through same API as regular storage access API. Could unify these all with login status API.
        * Johann: So wouldn't be needed if we had login status with additional flag to permit storage access.
        * Ben: yes. I just put it on a separate function so we'd have something to argue against. 
        * Sam: where does user name / profile name fit?
        * Ben: this doesn't have any of that in this proposal at all - probably should be for all rSA.
    * Christian: how does this relate to the other proposal you've made elsewhere for a window.open function for an RP
        * Ben: It's related. A bit more related to my first - lightweight credential. 
        * Christian: So are you proposing this instead of those?
        * Ben: I'm feeling this out as something relevant for SAA and maybe being done anyway. If we're going to be giving a new API for storage access, if could it cover some of the federated identity cases too that would be great.
        * Nick: I don't see why that's great. Encouraging websites not to use the purpose API, and instead continue using 3PCs but without scary UI. Seems like the wrong direction for the platform.
        * Johann: we'll have some more details in privacy CG tomorrow on why we want to do something along these lines. If you could join that would be cool. We'll discuss challenges, eg. with browser-based heuristics. 
        * Ben: another proposal - federated login without IDP APIs. Had lots of discussion and interest, idea was to extend it to FedCM via optional extensions and the various issues floundered after I left for parental leave. 
            * fedidcg/proposals/issue/3
        * Johann: asked for feedback on auto-granting storage access when FedCM has been granted, which may help. We haven't gotten the feedback we were hoping for.  Also something we have to consider. 
        * Sam: Can we assume that autogranting SA after FedCM would be OK with Firefox?
        * MT: Yes, damage has been done
        * Ben: No privacy argument there. But Nick might have concerns about furthering use of 3PCs.
        * Nick: couldn't hear well enough, happy to follow up
* Achim: Will reconvene tomorrow morning at 9:30. And have breaking on Wednesday on login status. 

## Attendee list 

* Tim Cappalli (Microsoft Identity, co-chair)
* Achim Schlosser (European netID Foundation, co-chair)
* Ari Chivukula (Google Chrome)
* Rick Byers (Google Chrome)
* Christian Biesinger (Google Chrome)
* Kyle Den Hartog (Brave)
* Nick Doty (CDT)
* Gustavo Kok (Netflix)
* Mihai Cirlanaru (Google Android)
* Sarah Nogueira (Criteo)
* Lionel Basdevant (Criteo)
* Elias Selman (Criteo)
* Michael B. Jones (independent)
* Yi Gu (Google Chrome)
* Filipa Senra (Google Chrome)
* Benjamin VanderSloot (Mozilla)
* Johann Hofmann (Google Chrome)
* Helen Cho (Google Chrome)
* David Benoit (IE)
* Alexandre Nderagakura (No affiliation)
* Brianna Goldstein (Google Chrome)
* Chris Fredrickson (Google Chrome)
* Ben Wiser (Google Android)
* Nicolas Pena Moreno (Google Chrome)
* Yoshitomo Sakuma (Fujitsu)
* John Bradley (Yubico)
* David Waite (Ping Identity)
* Stephen McGruer (Google Chrome)
* Marek Blachut (HM Government)
* Nicola Tommasi (Google Chrome
* Christian Dullweber (Google Chrome)
* Tom Van Goethem (Google Chrome)
* Matthew Miller (Cisco)
* Brent Zundel (Gen)
* Nick Steele (1Password)
* Anders Åberg (Bitwarden)
* Sam Weiler (W3C)
* Erik Anderson (Microsoft Edge)
* Soumya Chakrabarty (JCB)
* Sameer Tare (Mastercard) 
* Aaron Coburn (Inrupt)
* Zacharias Törnblom (Sunet, Sweden’s NREN)
* Yen-Lin Huang (moda, Taiwan)
* Hyojin Song (LG Electronics)
* Jean Luc Di Manno (Fime)
* Tomofumi Okubo(DigiCert)
* Wanpeng Li (University of Aberdeen)
* Kaustubha Govind (Google Chrome)
* Kyra Seevers (Google Chrome)
* Evan Jacobs (Stripe)
* Pascoe (Apple)
