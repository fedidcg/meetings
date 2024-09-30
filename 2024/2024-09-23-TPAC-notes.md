# Notes: FedID CG/WG session, Monday, 23 September @ 16:30​–​18:00
  


# Agenda

* Administrivia  
  * Scribe volunteer(s)? \- bf  
  * Reminders:   
    * To contribute: [Community Group Membership](https://www.w3.org/community/fed-id/) or [Working Group Membership](https://www.w3.org/groups/wg/fedid/)  
      * Visitors still welcome\!  
    * [W3C Code of Conduct](https://www.w3.org/policies/code-of-conduct/)  
* Intro to the CG/WG  
  * 15 min: [FedID CG/WG Process Mechanics](https://github.com/w3c-fedid/Administration/blob/main/proposals-CG-WG.md) – Wendy  
    * Reminder to join CG or WG via “join” lists on w3.org  
  * [Cheat Sheet to items tagged in the FPWD](https://github.com/w3c-fedid/FedCM/wiki/Status-of-FPWD%E2%80%90identified-Issues) (FPWD \- First Public Working Draft)  
* Demos  
  * 5 min: State of the union with Yi  
    * A walkthrough of indiatimes.com, seznam.cz, mobage.jp, naukri.com, and aid.no  
  * 5 min: IndieAuth with Aaron  
    * webmention.io and lastlogin.net  
  * 5 min: gmx.de and web.de demo with Nicolas and Ashima  
  * 10 min: Sign-in with Google with Gina and Brian  
  * 20 min: Shopify with Yoav Weiss and Joel Antoci  
* Existing Stage 1 Proposals **moved to Tuesday**  
  * 30 mins: Lightweight FedCM Issues (list forthcoming) 
    * Lightweight demo with Ben/Johann/Erica  
    * [Is there a way to maintain UI hint freshness without falling back to heavyweight FedCM \#40](https://github.com/fedidcg/LightweightFedCM/issues/40)  
    * Proposed next steps for this work item  
      * Stage 2  
      * Draft spec text  


## Notes 

# Intros and Administrativa  
# CG/WG Process  
  - Wendy: here is the CG/WG process on how the various deliverables move [https://github.com/w3c-fedid/Administration/blob/main/proposals-CG-WG.md](https://github.com/w3c-fedid/Administration/blob/main/proposals-CG-WG.md)  
  - Stage 0: to understand the problem, open to all from the Community Groups  
  - Stage 1: understand also the solution, there is consensus from the group. Small features are issues, when there is a champion, they can ask chairs for a repo.  
  - Stage 2: proposals WG Adopted, with an Editor from the WG. We need also to have the support from the community, to understand if there are interest on this.  
    - Public but not huge commitment (definitely not a commitment to produce anything you’re prototyping or evaluating)  
    - Shout out to Sam Goto for helping with this doc drawing on prior art from elsewhere in w3c  
  - If you’re new to the process or trying to figure out where to help, note the interplay of iterative internal review as well as champions to guide later-stage drafts through horizontal reviews  
  - Sam : It is a work in progress to help us to incrementally build consensus.  
  - Wendy: Feel free to create a PR on [the process](https://github.com/w3c/process), process it here to help us, not to block us.  
    - Heather: Explicitly marking stages helps people jump in at any point (or catch up at TPAC sessions) — valuable signposting (as well as interest signaling); we’re making this very explicit and hope other w3c groups will adapt this method  
  - Heather: First public working draft — lots of issues opened by it, many of them blocking/serious
  - 
# Demos
## Demo 1: Yi Gu (Chrmome FedCM API)
- Demo \#1: Yi Gu (Chrome FedCM API, @yigu)  
  - Mobage (gaming portal, IdP for games) ; Times Internet — IdP, portal, but still cross-site FedCM onboarding and IdP; Seznam.cz — general-purpose/search-oriented portal; Ameda/aid.no; SIW Google accounts;  
    - Screengrabs from Chrome and Edge; also working with Gecko and Webkit   
  - Status quo: thousands of websites → 0.9% of pageloads in Chrome invoking this API today  
  - Q\&A  
    - Q: John Wilander (Apple): Screengrabs imply cross-site identification to RP, how is this happening?   
    - A: Browser is showing this to the user, but RP doesn’t know that yet (doesn’t even know whether this is being displayed to the user, until user clicks to proceed);   
    - Q followup: Do you or will you support a per-site/per-RP opt-out or disable prompt?   
    - A: Depends on how a site uses the API: per-load or per-click would be separately disabled/policy-applied; npm1: these disabling settings are already available to the user for the demoed flow; hiding a UI disables it, exponentially (i.e., the more times you close it, the more disabling is inferred); John: wouldn’t want the standard to mandate an annoyance;   
    - Sam Goto: I think the annoyance is hard to measure and model in the UI; one thing we’re looking at is omnibox pills (?); we’re also looking at AI to interpret/diagnose user intent here; we’ll demo button flows later, and nuance the semantics accordingly  
    - Brian Campbell: I too want to underscore the annoyance of over-offering Sign-In, particularly from Google as IdP; I fear this API could enshrine the worst of that and make it default everywhere, and would lobby for us to make opting out upfront/early part of the API (?)  
    - Q: Chris Needham: How does a website become an IdP, how does the user agent learn what IdPs are available to them, and how does the RP declare what IdP it wants to work with \[for a given RP? In general?\];   
    - A: Yi: I didn’t demo the whole context, was just zoomed in on the API; Heather: There is a FedCM breakout on Wednesday providing more exhaustive/informative overview of the current and planned API;   
    - Q Sam Goto: Precisely because intrusion (from the IdP and RP) is a concern, we think the browser needs to have at least as much;   
    - Brian Campbell: I disagree; the SP/RP is the one with a right to intrude; conflict of interest for the browser to suggest its own IdP…;   
    - Sam: But website/RP can be adversarial in many cases, so browser intruding can offer more agency than over-empowering the RP to intrude;  
    - Ben: I want to add on Brian’s point that there is a lot of risk of confusion or deception here; it’s unclear what information has already been shared, what is browser versus what is website; context-collapse might be nudging end-user towards a decision (something something post- 3rd party cookie desperation?)
    - 
## Demo 2, Aaron Parecki, webmention.io IndieAuth

- Demo \#2 — Aaron Parecki — webmention.io dynamic client registration experimental feature (stage 1? Behind feature flags in Chrome at least); this demo aims to show “how IdP shows up in the list”; previous demo models today’s NASCAR world (RP lists all pre-known trusted IdPs); but this demo shows the opposite, browser populating list from pre-known IdPs that the RP has never heard of;  
  - This is similar in trust model to email OTP — RP has never heard of your email server, but uses OTP and linkback to authenticate new IdP  
  - Status quo: end-user types in IdP domain from memory (cf. Mastodon, webmention, etc); FedCM experimental feature allows browser to provide without end-user having to remember and type it out;  
  - Not demoing the behind-the-scenes flow between IdP and RP;  
  - IndieAuth (on which this demo relies) is a 2018 W3C CG Note (https://www.w3.org/TR/indieauth/) that has recently been updated to modern OAuth (https://indieauth.spec.indieweb.org/);   
  - Q\&A  
    - Johann: is the ecosystem ready for this new capability? Which IdPs know how to create the right token?   
    - Aaron: Fair question — FedCM doesn’t name or constrain tokens or say how IdP knows what token the RP needs or how RP filters on tokens; today, this is pretty proprietary; moving towards a standard for how that query happens is to-do here, but federation and/or certifications/brokers usually mediate (and save RP from having to know tons of IdPs or tokens in exacting details); how this would actually get implemented would be via communities clustering around (and nuancing) the “type” property being prototyped behind another feature flag, i.e., openBanking OIDC profile → a type, research IdPs that already recognize one another and coordinate → another type, etc;   
    - Johann: We’ve been exploring how to do this without a token-generating backend, and kind of assumed there would be a token? How is the IdP authenticated? Could this be faked?   
    - Aaron: no, but… \<chair interrupt- time\! It’s written up on GitHub)  
      - Write ups:   
        - [https://indieweb.org/FedCM\_for\_IndieAuth](https://indieweb.org/FedCM_for_IndieAuth)   
        - [https://github.com/aaronpk/oauth-fedcm-profile](https://github.com/aaronpk/oauth-fedcm-profile)   
        - [https://github.com/w3c-fedid/idp-registration](https://github.com/w3c-fedid/idp-registration)
          
## Demo 3: NPM, showing gmx.de and web.de 

- Demo \#3: npm1: gmx.de and web.de   
  - FedCM to date is 1 IdP at a time; the goal here was to help a single GET call pass an array of IdPs; origin trial in chrome 128 until early next year; main partner is netID (big european IdP) which is motivated to work on this because they operate across many domains and regional products,   
  - Note: this single-GET model doesn’t solve all multi-IdP cases, there are some better served by one GET per IdP;   
  - Screenshare: custom UI showing name, email, IdP-caveated PFP, and origin per IdP option  
    - Couldn't do live demo because project used geo-located and geo-checked EU IdPs and RPs  
  - Looking for more partners  
  - API isn’t that different, just changes one field to an array; fetches; other change is that content-URL is provided in response  
  - Q\&A: Ashima: note: if one of the IdPs are already signed-in, that gets bubbled up to the top of the UI;   
    - Heather: Come to breakout\!
## Demo 4, Sign in with Google, Active Mode origin trial 

- Demo \#4: Sign in with Google — Active Mode origin trial  
  - Gina: Pinterest, Canva, and LinkedIn are all trialing it with us;   
  - Vitalii: Not present in the demo: Continuation API (which would allow additional information for informed consent, etc.);    
  - Q\&A  
    - John: 2nd screen does what?   
    - Vitali: IdP has little additional info or consents;  
    - John: I think what the IdP learns about the RP is not what is concerning here, I want to know more about how much Google (qua browser aggregating) learns about which IdP is being used at which RP and user behavior;   
    - Yi: It’s not really shown in these screens, but there’s a graphic with a bi-directional arrow with RP and IDP… ;   
    - Sam Goto: we agree this disclosure is important ;   
    - John: I think the spec should be explicit about how much the end-user is shown about what info is being shared in all these directions, not just IdP⟷RP;   
    - ??: if i can nuance, RP/first party has a lot of control here over how much the IdP gets, and user-tracking vis-a-vis the browser/aggregator is important to the end-user, but here what we can control is how much the end-user learns about the RP⟷IDP info flows;  
- Chair interrupt: Lightweight moved to first slot tomorrow; this is important stuff to discuss because of UI hints;   
  - Ben: I think there are synergies here between my session tomorrow and Aaron’s webmention demo, since our IdP makes available little bits to RPs
## Demo 5, Joel Antoci (Shopify) 
- Demo \#5:   
  - Joel: Here from Shopify, talking about importance of signing in on ecommerce site, what FedCM enables us to do.  
  - SIW Shop \= buyer-facing ID platform for shoppers to authenticate themselves early (before checkout) to minimize friction to checkout, much higher conversion rate so super crucial to us to strengthen this .  
  - Ex: today’s “discount code in exchange for email verification” could be replaced by code being saved to shopID, thus authenticating earlier; testing shows big conversion bump for this; SIW Shop versus SMS OTP comparison: less friction; seller can check 3rd party cookie we share with them today.  
  - Passkey topic: we prefer it, helpful, *but* important caveat, requires explicit sign-in to *each* merchant across a shopping session, so FedCM is interesting to us because one sign-in can expose enough to each merchant not to need a separate passkey sign for each  
    - From chat:   
      - John Wilander: Also, the fact that the IdP knows the RP where the user chose to login doesn’t necessarily mean the IdP is tracking the user across domains.  
        Even if they aren’t, they can enrich their user profile by knowing that the user uses that particular website. Now combine that with ideas like targeting ads on one of the IdP’s websites.  
      - George Fletcher  
      - Yes, this is possible, not required by the IdP. However, I would agree with what someone else said. I don’t think most users see this as a significant privacy risk. The user wants the benefit of being able to federate the IdP account for many RPs.   
      - Yi Gu: From privacy perspective, the FedCM API does NOT tell IdP which RP the user is visiting before user permission   
  - Q\&A  
    - Npm1: I noticed in the demo that the FedCM UI popped up on load — was that intended/normative, or just a demo artefact?   
    - Joel: As a platform, we’re kind of a special case; we are incentivized already not to spam user, and know when and how to offer this; it’s a leap of faith for the end user to click this knowing it’s an authN mechanism, trusting the platform.  
    - Christian Indra: consent and trust work a little differently here, still exploring it.  
    - Joel: user sees they are authN’d, ; Yoav: Fence-frame with partitioned data combined with button mode is interesting.  
    - Sam Goto: We’re excited to expand the number of IdPs that can be represented in various flows. Does Shopify see value in being available off your platform and other IdPs being IdPs on your platform?   
    - Ilya: Small sites have all the odds stacked against them; large sites can afford to annoy or add friction, but small sites need help keeping fleeting attention. We are trying to find a UI that works for the health of our heterogeneous platform; the browser mediating is good in this case.  
    - Sam: if i can go further, would Aaron’s BYOIDP demo be useful to merchants?  
    - Ilya: what merchants want and benefit from is separate from (and more important than) what Shopify qua platform wants or allows…  
    - Anusha How is identity blinded for the RP?   
    - Joel: example of borrowing your partner’s credit card, and opting out of current AuthN state to fall back to “manually” entering CC info that mismatches controlled identity;  
    - John W: I want to insist that conversion rates or spending aren’t useful northstar metrics for a consentful identity API.  
    - Heather: That may be a little out of scope; private ad WG?  
    - Wendy: Devil’s advocate: IDP, RP, and end user, all have agendas and incentives and we have to understand how they all work toward API success.  
    - Ben vander: Optimizing for user agency.  
    - Ilya: Don’t take it too literally, we’re using conversion rate as proxy for friction being lowered.  
    - Ben vander: Privacy ⟷ friction is very complicated, and getting more complicated with loss of 3p cookies.  
    - Yoav: From platform’s perspective, user’s long-term interests matter more than short-term interests, i.e., end-user loyalty is a good proxy for user agency and protecting them from unwanted or deceptive transactions.

## Attendees {#attendees}

* Heather Flanagan (Spherical Cow Consulting)  
* Christine Runnegar (PING co-chair)  
* Aram Zucker-Scharff (The Washington Post)  
* George Fletcher (Capital One)  
* Benjamin VanderSloot (Mozilla)  
* Chris Needham (BBC)  
* Aaron Parecki (Okta)  
* Aaron Selya (Google Chrome)  
* Ben Wiser (Google Android)  
* Nicolás Peña Moreno (Google Chrome)  
* Christian Biesinger (Google Chrome)  
* Erik Anderson (Microsoft Edge)  
* [elf Pavlik](https://elf-pavlik.hackers4peace.net) (independent, Solid CG)  
* Yi Gu (Google Chrome)  
* Alan Buxey (MyUNiDAYS Ltd.)  
* Erica Kovac (Google Chrome)  
* Bumblefudge (Protocol Labs)  
* Brian Daugherty (Google Identity)  
* Martin Alvarez (Huawei)  
* Vitalii Tomkiv (Google Identity)  
* Nick Watson (Google Identity)  
* Niklas Merz (The Apache Software Foundation)  
* Johann Hofmann (Google Chrome)  
* Chris Fredrickson (Google Chrome)  
* Zachary Tan (Google Chrome)  
* Shivani Sharma (Google Chrome)  
* Wendy Seltzer (Tucows, invited expert)  
* Ty Everett (BSV Association)  
* Brayden Langley (BSV Association)  
* Jake Jones (BSV Association)  
* Brett Banfe (BSV Association)  
* Simone Onofri (W3C)  
* Nick Doty (CDT)  
* Yoav Weiss (Shopify)  
* Lionel Basdevant (Criteo)  
* Aloïs Bissuel (Criteo)  
* Anusha Muley (Google Chrome)  
* Andrew Pascoe (NextRoll)

## Regrets

* Ted Thibodeau (OpenLink Software) — conflicts with DID WG

