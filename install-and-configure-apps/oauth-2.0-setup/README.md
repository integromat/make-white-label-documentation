# OAuth 2.0 setup

Some apps require an OAuth 2.0 connection to function on your instance. For example, Slack and Google Sheets need OAuth 2.0 credentials to access the relevant APIs. OAuth 2.0 configuration requires the following:

* A **Client ID** and **Client Secret** from the third-party app you want on your instance. In most cases, you need a developer account with the third party to get the required credentials.
* A **redirect URI**. You can find the appropriate redirect URI at **Administration > Native apps > {app} > Connection in the Account parameters** section. The general pattern for redirect URIs is: `https://{yoursubdomain}.integromat.celonis.com/oauth/cb/{app_name}`
* Enabled third-party scopes. Each module requires specific scopes to access the third-party app.

{% hint style="info" %}
There may be multiple versions of an app if there are multiple API versions. You can add any number of versions as you want.
{% endhint %}
