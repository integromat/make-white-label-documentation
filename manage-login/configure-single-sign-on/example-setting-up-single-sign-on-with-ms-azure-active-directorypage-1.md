# Example: Setting up single sign-on with MS Azure Active DirectoryPage 1

Microsoft Azure supports both OAuth 2.0 and SAML 2. Perform the following steps to connect Make with Azure Active Directory.

### OAuth 2.0

1. Log in to your Azure Portal and open Azure Active Directory.
2. Open App registrations and click **New registration**.
3. Give the registration a name.
4. Fill in the Redirect URL.
   * Find the Redirect URL In **Make > Organization > Settings** after you select an SSO type.
5. Click **Register**.
6. Note down the Application (client) ID.
   * Paste this ID into your Make settings.
7. Go to **Certificates** and secrets and click **New client secret**.
   * Paste the secret value into your Make settings.
8. Go to **Overview** and click **Endpoints**.
   * Paste the OAuth 2.0 authorization endpoint (v2) into the Authorize URL field in Make settings.
   * Paste the OAuth 2.0 token endpoint (v2) into the Token URL field in Make settings.
9. Paste the following into the **User information URL** in Make settings.
   * [https://graph.microsoft.com/v1.0/me](https://graph.microsoft.com/v1.0/me)
10. In Make, set up Login scopes and Scopes separator:
    * Login scopes: `openid`, `profile`, `email`
    * Scopes separator: space
11. In Make, paste the following into User information IML resolve. This tells Make how to map user information received from Azure to information in Make database.
    * `{"id":"{{id}}","email":"{{mail}}"}`
