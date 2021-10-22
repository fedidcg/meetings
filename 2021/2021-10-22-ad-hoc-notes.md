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

User Stories
------------

-   [<u>User Story: Service collecting username, dynamically disclosing
  options for explicit authentication flow w/without federation
  service
  \#6</u>](https://github.com/fedidcg/use-case-library/issues/6)

    -   Achim: This is not really a 3p cookie-related story; it is
      looking at a broader pattern of impact. This use case is one
      deployed by several partners and tries to deal with the NASCAR
      problem. This is also called “identity first login
      experiences”. Instead of providing an email, password, and
      several fed id providers, I ask the user to select the
      preferred username and then there is no differentiation
      between sign up and sign in, and the user is guided through
      the experience. As soon as the user provides their username,
      the service decides what the next steps should be. This can
      easily look like tracking due to the information being passed
      in the protocol. The user wouldn’t expect to need to enter the
      account multiple times during the flow; the information would
      be passed automatically and behind the scenes.

    -   Kris: This is also a subset of the e-commerce scenario and
      payment wallets go through the same situation.

    -   Achim: It doesn’t matter if it’s sign-up, sign-in, or payment.
      Also known as staged disclosure.

    -   Brian: This pattern puts the user in a tricky position - you
      show up at a website with different options, and you may be
      using the option you used last time or you may use another, at
      which point you create a joining of information about you.

    -   Kris: Would expect this to be something Apple’s new “hide my
      email” feature would create an issue, potentially creating new
      usernames/accounts for the user.

    -   Brian: not sure the Apple email is transient. It might be one
      that forward to the primary inbox?

    -   Kris: it is transient in that you can manage it and have it be
      new each time.

    -   Brian: that’s a new layer of responsibility on the user to
      remember what they’ve used and where.

    -   Achim: this is another thing that won’t work because the user
      won’t know all their email addresses, unless they are only on
      an Apple device.

    -   Brian: What’s the likelihood that the user is going to easily
      and simply interact with this and not get stuck in the UX.

    -   Kris: There is a lot of context about what a user wants to
      provide when they’re using certain things. It’s different when
      they’re just accessing the site versus what they’d be willing
      to offer when they are making a purchase.

    -   Achim: What happens with these transient email addresses, the
      server will eventually ask for your real email address to
      complete the transaction.

-   [<u>User Story: Federated Login Service with IdP Federation
  \#7</u>](https://github.com/fedidcg/use-case-library/issues/7)

    -   Achim: we talked about this during Kris’ use case and decided it
      needs its own user story. A federated service can allow a user
      to choose between multiple IdPs but not the service itself.
      The user can indicate to the login service their preference
      for what account to proceed with for their experience. From
      the service perspective, this would be one federated login
      service; from the user, they get to choose and assume their
      assertions are handed from the IdP to the service. These would
      be visible first parties they are interacting with, so they
      wouldn’t be surprised about the information passing back and
      forth.

    -   Brian: in terms of returning of assertions, could that happen
      directly between the IdP and the service?

    -   Achim: Theoretically yes but practically no; you would have to
      have multiple integrations with the service that would allow
      it to act almost as an IdP.

    -   Brian: what about at the point of contact, saying when you have
      a contact, go to this endpoint? I go to a website, and I want
      to use my Microsoft email address. I put that in, that goes to
      a federation server and says it is a Microsoft address and
      sends it to Microsoft to validate. Can Microsoft go straight
      back to the service or does it have to go through the
      federation service?

    -   Heather: in an academic federation, yes, it can go directly back
      to the service.

    -   Achim: yes, but this use case is a B2C model so it’s a different
      use case.

    -   Achim: to the 3p question, this could also use 3p integrations
      which would require on user’s prior sign ups. That would be
      additive to this story, not a different one.

    -   Heather: there is a story that focuses on a “smart button”
      scenario (see
      [<u>https://github.com/fedidcg/protocol-library/blob/main/src/cross\_origin\_discovery.md</u>](https://github.com/fedidcg/protocol-library/blob/main/src/cross_origin_discovery.md))
      that is very 3p contingent

Open Discussion

-   Heather: we’re going to have a general library of user stories that
  will be useful when comparing against different solutions. Note
  that FedCM will just look at 3p cookie issues. Interesting to see
  that PrivacyCG is still arguing about definition of “tracking” and
  that’s going to impact any further technical solutions for things
  like link decoration and bounce tracking.



Attendees
=========

-   Bill Densmore, ITEGA.org

-   Achim Schlosser

-   Tim Cappalli (Microsoft, co-chair)

-   Kris Chapman (Salesforce, co-chair)

-   Heather Flanagan (Spherical Cow Consulting, chair)

-   Brian May

-   Emily Lauber
