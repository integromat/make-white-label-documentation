# Steps in Google Developer Console

Creating your credentials involves the following general steps:

1. [Create a project on the Google Cloud Platform Console (optional)](steps-in-google-developer-console.md#create-a-project-on-the-google-cloud-platform-console)
2. [Configure your User consent screen](steps-in-google-developer-console.md#configure-your-user-consent-screen)
3. [Add scopes](steps-in-google-developer-console.md#add-scopes)
4. [Create your OAuth credentials](steps-in-google-developer-console.md#create-your-oauth-credentials)

### Create a project on the Google Cloud Platform Console

This procedure is optional. If you already have an existing OAuth app, you can add your Make redirect URI and any necessary scopes.

1. Go to the Google Cloud Console Platform.
2. From the projects list, select a project or create a new one.
3. Click **APIs & Services**.
4. Click **+ Create credentials**.
5. Select **OAuth Client ID**.
6. Click **Configure** **consent screen**.
7. Select **Internal** or **External** based on your implementation.
   * **Internal** if you only intend users within your Google organization.
   * **External** if you want anyone with a Google Account to use Google apps on your instance.
8. Click **Create**.

The page for setting up your consent screen appears. Use the information in the following section to complete configuration.

### Configure your User consent screen

These options in the Google Developer Console let you customize the consent pop-up that your users will see when configuring a connection on your instance.

| Customizing option            | Description                                                                               |
| ----------------------------- | ----------------------------------------------------------------------------------------- |
| Application name              | 3.11.18                                                                                   |
| App logo                      | Upload an image that your users will see when they create a connection for their modules. |
| User Support Email            | Select your email                                                                         |
| Authorized domains            | `make.com`                                                                                |
| Developer contact information | Enter your email                                                                          |

### Add scopes

After configuring your consent screen, the next page asks you to add scopes.

In the **Scopes for Google APIs** section, enter the required scopes for the Google service you want to connect to Make by checking the corresponding box for each required scope.

### Create your OAuth credentials

1. In the left menu, click **Credentials**.
2. In the **Application type** field, select `Web application`.
3. In the **Name** field, enter the name you want for your application.
4. You need a redirect URI for the **Authorized redirect URIs** field. You can find this by going to **Administration > Native Apps > \[Google App] > Connection**. Your redirect URI appears in pink letters after the text.

{% hint style="info" %}
Most apps for Google services require more than one OAuth connection. For example, one named `Google` and another named `Google restricted`.
{% endhint %}
