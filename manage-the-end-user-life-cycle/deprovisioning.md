# Deprovisioning

When you need to deprovision a customer from your instance, using Make API allows you to automate the process and offers more functionality than the Administration interface. The recommended procedure is to set all consumables to 0 and give the customer limited access to the organization. This way preserves their scenarios and data in the event that the customer decides to subscribe again.

1. Use the license object to set operations and other consumables to 0 or the minimum value. This configuration freezes the organization and its scenarios while allowing former customers to have access to their data stores and other assets associated with their organization.
2. Transfer organization ownership to a dummy owner that you create. Reassign the end user to a role with limited access, such as member. This step limits the former customer's permission privileges while preserving their data and other assets for later use if the customer returns.

You can verify the deprovisioned user's access by using the **Login as user** feature on **Administration > Users > Detail**.

Once you click **Login as user**, you immediately see that user's dashboard. You can edit the deprovisioned user's notification settings so they do not receive notification emails.

To return to Administration, you need to log out as the user and then log in with your credentials.
