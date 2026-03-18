# Steps on the Meta for Developers portal

To create OAuth 2.0 credentials for Facebook and other Meta apps, follow these general steps:

1. [Create an app on the Meta for Developers portal.](steps-on-the-meta-for-developers-portal.md#creating-an-app-on-the-meta-for-developers-portal)
2. [Add products to get the permissions required by Make's Facebook apps.](steps-on-the-meta-for-developers-portal.md#adding-products)
3. [Find your OAuth credentials.](steps-on-the-meta-for-developers-portal.md#finding-your-client-id-and-secret)
4. [Test your OAuth connections and add required permissions.](steps-on-the-meta-for-developers-portal.md#testing-and-adding-permissions)

### Creating an App on the Meta for Developers Portal

Follow the [instructions provided by Meta for how to create an app](https://developers.facebook.com/docs/development/create-an-app/). Use the following information to complete the procedure as documented by Meta:

1. Choose an app type: Select **Business**.
2. Choose a use case: Select **Other**.

### Adding products

To access the required permissions, you add what Facebook calls products. Each product represents a unique set of API access. Facebook Login for Business enables access for most Make apps modules. Refer to the chart below for more details.

#### Facebook Login for Business

The default settings are compatible with your Make White Label instance and require no adjustments. However, you need to enter your OAuth redirect URI in the settings for Facebook login for business.

1. In the Meta for developers portal, go to the [App dashboard](https://developers.facebook.com/docs/development/create-an-app/app-dashboard) for your app.
2. In the left sidebar, click **Add product**.
3. Find **Facebook login for business**.
4. Under **Client OAuth settings**, enter your OAuth redirect URI in the field **Valid OAuth Redirect URIs**.
5. Click **Save changes**.

Refer to the table below and add any additional products required by Make's apps.

### Finding your Client ID and secret

Adding Facebook login for business lets you begin using Facebook's API. You can now find your OAuth credentials and enter them in your instance.

1. In the Meta for developers portal, go to the **App dashboard**.
2. Click **Settings**.
3. Click **Basic**.
4. Find the **App ID** and copy paste it into the **Client ID** field on your Make instance at **Administration > Native apps > {Facebook app} > Connection: Facebook**.
5. Find the **App secret** and click **Show**.
6. Copy paste the App secret into the Client secret field on your Make instance at **Administration > Native apps > {Facebook app} > Connection: Facebook.**
7. Click **Save** on your Make Native apps connection page.

You can now test Facebook apps in scenarios. Without completing Meta's [app review](https://developers.facebook.com/docs/resp-plat-initiatives/individual-processes/app-review) and [business verification](https://www.facebook.com/business/help/1095661473946872?id=180505742745347) you have limited API access to Facebook. As a result, some modules may encounter errors. The Testing and adding permissions section has information on gaining further Facebook API access.

### Testing and adding permissions

You can request access to specific permissions by going to **Meta for developers > App Dashboard > App Review > Permissions and Reviews**. The Permissions and Reviews page lists permission and includes unsuccessful attempts from modules on your Make instance. Use this page to request access to specific permissions and find information about any further requirements.
