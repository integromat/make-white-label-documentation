# Shared webhooks

A shared webhook sends event data from the app to a single URL for each Make instance. Make then forwards the payload to the webhook in the scenario based on the metadata in the payload. For example, the Slack app uses shared webhooks. Make uses shared webhooks rarely, only in case there is no other implementation option.

To configure apps that use a shared webhook, use the shared webhook URL for the app and its specific version.

The following is the general process for finding the shared webhook URL for the app:

1. Go to **Administration > Native Apps**.
2. Click the app you want to set up.
3. Select the version of the app.
4. Find the webhook URLs under Shared webhooks.
5. Click the copy icon to copy the URL.
6. Paste the URL into the third-party page. The location of the webhook settings depends on the third party.

You have set up the shared webhook for the app. Your users can now use the app's instant trigger modules in their scenarios.
