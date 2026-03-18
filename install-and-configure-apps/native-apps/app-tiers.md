# App tiers

Make White Label lets you designate tier levels for apps. Tiers limit access to apps so that only specific end-users can use those apps in their scenarios. For example, Make uses tiers to offer a premium level of apps reserved for **Enterprise** customers.

You can assign app tier levels by entering an integer between 0 and 3 in an app's configuration page. 0 means that the app is available to all organizations. 3 indicates the highest premium tier. Each tier level includes all apps from lower tiers. For example, tier 2 includes tier levels 0, 1, and 2.

You can then define an organization's access to premium tiers via the organization's [license object](/broken/spaces/LXp8X1eBwkwrLIWrN9cg/pages/rL2Vlf2izrW74G5jDqvy).

1. Go to **Administration** > **Native Apps** > **{app}**.
2. Under **Premium app**, use the arrows to assign an integer from 0 to 3 inclusive.
3. A confirmation message briefly appears. You can now use the `premiumApps` parameter of the license object to control access.
