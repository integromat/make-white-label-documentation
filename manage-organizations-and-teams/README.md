# Manage organizations and teams

Make White Label offers the same structure for organizing users and their access as the Make public cloud. To manage user access to scenarios and resources, Make features two hierarchical levels for groups of users:

* Organizations - the higher level that typically represents your end customers. End-users can invite new users to their organization to share their scenarios and other resources. Organization roles, such as owner and member, represent sets of permissions and access.

{% hint style="success" %}
For white label use, it's best practice to use an organization for each customer. Using organizations this way isolates your end customers and restricts access to only the scenarios, templates, etc. that end-customer creates. The core concept is that one organization represents one end customer.
{% endhint %}

* Teams - a sub-level for finer-grain access management. End users can assign their organization members to different teams to further manage access.

{% hint style="info" %}
The public UI lets you administer teams. [See our public documentation for details](https://www.make.com/en/help/access-management/teams).
{% endhint %}

For example, one of your end customers is Acme, Inc. Acme, Inc. wants automations for their sales and HR team. As the instance administrator, you can give Acme, Inc. an organization and the ability to create and manage teams within that organization. Acme, Inc. creates two teams: one for sales, and another for HR. The owner of Acme, Inc's organization can invite new users to specific organization and team roles.

Organizations also contain the following:

* Scenarios
* Templates
* Teams
* Data stores
* Data structures
* Custom apps

{% hint style="info" %}
Create scenarios, templates, data stores, data structures, and custom apps in the organization or team you want them to belong to. Once created, there are few options to reassign these assets to a different team or organization.
{% endhint %}

