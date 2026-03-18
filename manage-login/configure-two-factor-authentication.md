# Configure two-factor authentication

Make White Label supports two-factor authentication (2FA), such as Google's Authenticator app. The following procedure enables 2FA for your instance. End-users must complete the process by going to their profiles and using Google Authenticator or a similar app.

1. Go to **Administration > System Settings**.
2. Select **Enabled** from the **Two Factor Authentication** menu.
3. For **Two Factor Authentication app name (visible in Google Authenticator)** enter the name you want to appear in the authentication app.

{% hint style="info" %}
For more information, go to the [user documentation on 2FA](https://www.make.com/en/help/access-management/two-factor-authentication).
{% endhint %}

Your instance now allows end-users to set up 2FA. Verify by clicking **Leave administration** and going to **Profile > 2FA**. When a user sets up 2FA, a window opens with the QR code for Google Authenticator or similar apps. Scan the QR code and enter the numeric code in the field.
