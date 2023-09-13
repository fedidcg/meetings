# FedID CG notes, 11 September 2023 (TPAC)

Scribe: 
* Benjamin VanderSloot
* Starting frorm Testbed Nicolas Pena Moreno

## Agenda

* Welcome & Administrivia (09:30-09:35)
  * Scribe volunteer(s)?
  * Reminders: 
     * [Community Group Membership](https://www.w3.org/community/fed-id/)
     * [W3C Code of Ethics and Professional Conduct](https://www.w3.org/Consortium/cepc/)

* FedCM demo and browser status (cont'd) (09:35-10:00)
  * Brave (in case we have representation)
  * Safari (in case we have representation)
 
* Status of [testbed](https://github.com/fedidcg/fedcm-testing) and how to use it (10:00-10:15)

## Notes

* Tim:
  * Big conflict with Privacy CG today, so we are working on a shortened agenda, continuing demos
* No complaints heard
* Nicolas continuing chrome’s demos from yesterday, doing future work to ship in upcoming chrome versions
    * IDP sign-in status API (this month?)
        * Rationale: mitigate the Timing Attack
        * Login/out recorded by the IDP 
        * Log out state tells the user agent it can fail without UI
        * Logged in state tells the UA to show a “you can use your account” dialog on page-load
        * Logged in but no accounts, state tells the UA it can create a popup which can log the user into a new account
        * Feedback:
            * Concerns that popup UI is below the line of death and looks a lot like browser UI
            * This looks a lot like payments, maybe that would work better!
                * Google Security is unhappy with this compared to our solution
                * Users can move a popup to tell that it is a window
            * Ben: Do redirect flows  work in FedCM with sign in status?
                * Npm - maybe, but it would require multiple calls to n.c.g
                * Not supported
                * Maybe an extension
                * Maybe privacy issues of disclosure of the RP to the IDP.
            * Tim: sign in without context is semantically confusing for many IDPs
            * Zacharias: How does the RP know what IDPs to populate because I have thousands!
                * Npm - it is the RP’s job based on context
                * We are working on the multi-IDP- demo later
                * Discovery is hard
                * Zacharias: Do you want my comments on this now or later?
                * Achim: this is probably very hard for multi IDP and we have had a lot of feedback from lots of academic IDPs that have this concern. But maybe this could help if you can show a prompt for where the user is already logged in
                * Christian: Maybe it could be done
                * Ben: might be some privacy concerns about feedback of the logged in state to the RP
                * Npm: We agree with those privacy constraints
                * Ben: very speculative, sorry
                * Someone: What about “logged in anywhere” bit, like personas!
                * Christian: has problems of its own
                * Group: knowing muttering
    * Error code API (in OT)
        * If the IDP errors, we get a door-hanger that says errors happened and buttons to learn more and dismiss. Learn more opens a popup.
    * Account AutoSigned
        * In case Account is autoselected this information is provided to IDP/RP
    * Hosted Domain:
        * Similar to LoginHint, allows filter of accounts presented to user
        * Allows filtering account on a given Domain
        * Example - only shows user with gmail, without filter all accounts
    * Revocation
        * No Demo
        * Allows RP to revoke the users approval status IDP/RP pair
        * Can also be called from an IDP IFrame
    * Alex:
        * How does the filtering work?
    * Nicolas:  
        * Filtering is within IDP if its hosting multiple Domains
    * AuthZ
        * IDP Shows Pop, if RP is requesting permission different from the regular sign-in scope. For example RP want access to calendar
        * IDP will to explicitly agree, using an additional UI
        * Once confirmed - IDP will return token to RP to enable access
    * Multi-IDP
        * User in the demos is logged into multiple IDP, based on the RPs selection of IDPs 
        * Selector will show accounts from multiple IDPs
        * Accounts are grouped by IDP in the selector
        * After account is selected it continues as usual
        * Several complications with this API
    * Question
        * Michiel
            * There might be multiple allows, but user would not be logged into more then 2-3 (don't need to fetch all of them)
        * Nicolas 
            * would  registration of IDPs which is not the case
            * What would happen if user is not logged into one
        * Michiel
            * FedCM could fallback to the exiting account selector
        * Achim
            * Very important API for market acceptance
        * Nicolas
            * Agree its an important topic

Scribe: Nicolas Pena Moreno

**Testbed**

* Achim: FedCM API behaves differently from the normal scenarios, so there have been discussions in the CG about how folks evaluate or engage with their own stakeholders, as well as how to implement. It’s a complex API, so nobody is just going to throw that into production.
* Currently we have two prototyping environments. These live in the repos of the folks who implemented them. W3C largely has licensing for code as it relates to testing suites.
* Demo: fedcm-testing within the fedidcg GitHub. There is a SpringBoot/Java implementation and there is a Node.js/JavaScript implementation. Each have descriptions about how to build and run them. There was an issue before but now you can run everything on localhost. You can include various IDPs within the same instance. It includes a bunch of the features that have been presented already.
* I’m running both RP and IDP implementation with a local server. You can see the relying party implementation. That UI is from one of the standard Chrome demos, but generalized to being configurable. The IDP one is a generic sample IDP which has a basic login experience.
* First thing you need to do is create an account. We have passkey support for the kicks. So you can see the test user account. Going back to the RP demo, this is configured to trigger FedCM on click. I get the FedCM prompt with the user data that I just registered, and I continue with the flow.
* What you can then do is the RP side configuration options. You can switch from user activation to on page load. Autosignin is triggered since I used it before. You can play around with the different options. You can see the page-load experience can be annoying as it blocks some of the RP UI.
* You can configure mediation, context, enable user info, and also scope, although this is not fully implemented. I think it also has signin URL support. The session has a 3 minute timer or so.
* It also has visualization for approved clients. You can record the approval status, which enables auto sign-in. And you can manipulate that. You can see disclosure text is not shown when approved, but once it is removed, the browser will show the disclosure text.
* Both us and education folks can maintain demos and see where we can go.
* There are a lot of details. The config defines supported clients. You can just configure different IDP domains. You can create more instances. For us, multi IDP is super important. We’re looking for feedback in terms of how the CG should continue on that. I think anyone working on this needs something to understand how it works: you can’t just give them the specification.
* Michiel: Are you talking to university networks
* Achim: yes. I think that there is no solution found yet for these cases but there is active discussion.
* Michiel: For me coming from the Solid WG, that is interesting. But there you can login with any IDP. Is that something that could be supported. Like if an RP says any IDP will do. It would be cool if it could remember my WebID.
* Achim: part of that Chrome has implemented, with auto signin. I think the other question is “just use any”. For us, that wouldn’t work, but I think there is nothing that technically stops it from happening. For now, separating federation and wallets. There will be some wallet discussions on Wednesday.
* Michiel: two separate problems. A lot of buttons, would be nice to have less buttons. The other one is to remember that any URL could be an IDP. For Solid, we do want that.
* Achim: there is a large history of discussions around the Nascar problem. If there are no legal necessities in terms of IDPs, I think why not. We have a charter discussion on Thursday but the WG is now focused on federated use-cases and the wallet stuff is going on incubation in another group.
* Michiel: have you talked about authorizing other scopes than identity.
* Achim: yea that was the authz which was shown. We agreed it shouldn’t be called authz, but yea that is ongoing. But again in my personal role, I think it must be supported.


## Attendee list 

* Zacharias Törnblom (SUNET, Sweden’s NREN)
* Tim Cappalli (Microsoft Identity, co-chair)
* Ben VanderSloot (Mozilla)
* Christian Biesinger  (Google Chrome)
* Alan Buxey (MyUNiDAYS Ltd.)
* Achim Schlosser (European netID Foundation, co-chair)
* David Waite (Ping Identity)
* Martin Alvarez (Huawei)
* Pascoe (Apple)
* Yi Gu (Google Chrome)
* Nicolas Pena Moreno (Google Chrome)
