# Alternate option: require user-provided credentials

If you do not want to share your OAuth 2.0 connection, you can leave the credential fields blank. Leaving those fields blank requires end-users to enter their own OAuth 2.0 credentials in the Scenario editor.

You must then provide end-users with a redirect URI because your end-users need that redirect URI in order to create their own Client ID and Client secret. Make's public help center has information on how end-users can do this themselves.

{% hint style="warning" %}
Make's UI does not inform end-users that they must create and provide OAuth 2.0 credentials. Therefore, we recommend you inform your end-users and provide them with the necessary information.
{% endhint %}
