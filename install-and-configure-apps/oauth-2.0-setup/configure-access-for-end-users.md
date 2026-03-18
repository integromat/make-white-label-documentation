# Configure access for end-users

Facebook, Google, and other apps require an OAuth 2.0 connection. In these cases, you need OAuth 2.0 credentials from that third party. For example, Google requires you to create an app on the Google developers console.

Entering your credentials on your Make White Label instance creates a connection that enables users to use that app's modules in their scenarios and access their data. For example, entering Facebook OAuth credentials allows users to connect their Facebook account to Facebook modules in their scenarios. In these cases, the credentials you enter for an app on the Native apps page create a 'parent connection' that enables users to create their 'child connections'.

The following procedure creates an OAuth 2.0 connection accessible to all users on your instance. This configuration gives your end-users access to the third-party app via the credentials you enter and save at **Administration > Native apps > {App} > Connection**. End-users must still grant permission. For example, Google asks end-users to grant permission and allow access to their Google account. End-users need only their account credentials to grant permissions.

1. Go to **Admin > Native Apps** and click the third-party app you want to configure.
2. Go to the **Connection** tab and enter your Client ID and Client secret.
3. Click **Save**.

The Client ID and Client Secret appear in JSON format in the Common data field.
