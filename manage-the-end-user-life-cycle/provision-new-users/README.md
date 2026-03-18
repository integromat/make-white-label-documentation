# Provision new users

To provide your end users with access, you need to provision them by creating both a user account and an organization. Although the admin UI lets you create new users and organizations, API is the best method to provision new users because it lets you automate the process and also lets you define the license of new organizations. You can use these API endpoints in scenarios to provision new users. For instance, the contracting event in a CRM app can trigger your scenario to create an organization and user on your instance.

The following are the main tasks required for provisioning new users:

* [Create the user](create-users-and-organizations.md) if they do not already exist on your instance. Create the user first so you can later assign them to organizations and teams with appropriate roles. The best practice is to create the user and send an invitation without defining their password.
* Create an organization for the customer. You need to [define the license](define-the-organizations-license.md) of each new organization on your instance. The license includes many parameters that allow you to control access to features and limit usage. If not otherwise defined, all new organizations inherit your instance's default license.

You can automate the above tasks via Make scenarios you create to suit your specific needs. Remember that you can integrate provisioning tasks with your customer onboarding.
