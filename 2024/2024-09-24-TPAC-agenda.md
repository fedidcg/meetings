# FedID Joint CG/WG Session - TPAC 2024
## Tuesday, 24 September @ 11:00-12:30
Scribing doc [link](https://docs.google.com/document/d/1_M7PS9ZRhSUGsV9QnzArNc3BA9i8A2nS0PnfcngABas/edit#bookmark=id.v729wj6uovg0)

## Draft Agenda - Tuesday
* Administrivia
   * Scribe volunteer(s)?
   * Reminders: 
     * To contribute: [Community Group Membership](https://www.w3.org/community/fed-id/) or [Working Group Membership](https://www.w3.org/groups/wg/fedid/)
        * Visitors still welcome!
     * [Code of Conduct](https://www.w3.org/policies/code-of-conduct/)

* [IdP Registration API](https://github.com/w3c-fedid/idp-registration)

* Lightweight FedCM Issues
       * Lightweight demo with Ben/Johann/Erica
       * Is there a way to maintain UI hint freshness without falling back to heavyweight FedCM - [issue #40](https://github.com/fedidcg/LightweightFedCM/issues/40)
       * Proposed next steps for this work item
           * Stage 2
           * Draft spec text
* Proposal looking to advance to Stage 2
   * 30 min: Button Mode – Yi ([slides](https://docs.google.com/presentation/d/1WRGI1BlPnqRwRs40w1j1nOEYBHwDAEaNEljcTReoOic/edit#slide=id.g300c7805003_0_1383)): 
      * Issue 442: A not-yet logged in IDP has no route to success with this flow 
   * 30 min: Custom Requests – Christian ([slides](https://docs.google.com/presentation/d/1WRGI1BlPnqRwRs40w1j1nOEYBHwDAEaNEljcTReoOic/edit#slide=id.g300c7805003_0_1387))
      * Issue 555: Allow IdPs to continue and finish the request in a popup window
      * Issue 556: Passing arbitrary parameters to the ID assertion endpoint
      * Issue 559: Allow RPs to selectively request attributes of the user’s profile
   * 10 min: Account Labels – Christian ([slides](https://docs.google.com/presentation/d/1WRGI1BlPnqRwRs40w1j1nOEYBHwDAEaNEljcTReoOic/edit#slide=id.g301c1ee8389_2_4))
      * Issue 553: Allowing IDPs to expose different account lists in different contexts
   * 10 min: Multiple configURLs – Christian ([slides](https://docs.google.com/presentation/d/1WRGI1BlPnqRwRs40w1j1nOEYBHwDAEaNEljcTReoOic/edit#slide=id.g300c7805003_0_1387))
      * Issue 552: Allow IDPs to use multiple config files within an eTLD+1
