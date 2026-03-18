# Manage the end-user life cycle

Make White Label administrators rely on the following principles to manage end users:

* **A customer is an organization** - Make's organizations provide a structure that lets you grant only the access that you want to share with each end customer. Assigning each end customer to an organization lets you use the following to customize access:
  * License parameter - each organization has an independent license that contains definable parameters. The license parameters let you assign a custom set of limits, features, and access for each end customer.
  * Permission roles - every user has defined roles for the instance, organization, and team level. Making each end customer the owner of an organization lets you use their license parameter and role to control their access to your platform's resources and data. Assigning end customers to organizations also isolates your end customers from each other.
* **Every organization has only one owner** - although an organization can have multiple administrators, only one user can be the owner. Again, the standard practice is to designate the owner of the account as the organization owner. This arrangement gives your customer the most authority over their own organization and allows them to invite users to their organization and assign organization roles to their organization members.
* **Any user can belong to multiple organizations** - end users do not need to own an organization to have access to it. If you allow it in their license, end customers can invite new end users to their organization. For example, in a B2B SaaS use case, a company is your customer. They may have several organizations and multiple users on your instance to automate and collaborate.

The following tasks represent the customer/user life cycle. Use the links to access more detailed information:

1. [Provision new users](provision-new-users/) - You need to add every new user to the platform and create an organization for them. Although the SSO options let you do this automatically, creating your own automation and using admin API endpoints is a better method. The admin API endpoints provide more possibilities including defining the license to limit the new customer's access. The admin API also lets you assign roles to further define the new customer's access to your platform.
2. [Maintain users and organizations](maintain-end-users/) - Administrative tasks such as resetting passwords and enabling features for your internal app developers.
3. [Deprovision](deprovisioning.md) of customers.
