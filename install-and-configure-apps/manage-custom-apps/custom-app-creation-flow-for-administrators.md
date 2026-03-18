# Custom app creation flow for administrators

The following sections describe the main stages of app visibility and the related administrative procedures.

## Private app

All custom apps begin as a private app. Only instance-level admins and the user who creates the app can access it in the apps platform and develop the app.

Private apps can be shared within an organization by [installing them](https://app.gitbook.com/s/NS0mCBwODiYtOVXjc6qf/create-your-first-app/app-visibility#private-app). An instance-level admin can install the app to an organization by logging in as a user:

1. Go to **Administration > Users**.
2. Find the user who created the app and click **Detail**.
3. In the upper right, click **Login as user**.
4. Once logged in as the user, create a scenario using any module from the private app.
5. Save the scenario.
6. In the popup, confirm the installation of the private app in the organization.

{% hint style="info" %}
If you don't know which user created the app, you can find this in the **Author** column of **Administration > Apps**.
{% endhint %}

Once installed, all organization members can use the custom app's modules in their scenarios.

## Public app

A public app is a custom app that the creating user has published. Like an installed private app, it appears for all organization users when they build scenarios. The difference is that the creating user has a link to share the app with any user on your instance. They share this link by copy-pasting it into an email or messenger app. The link recipient then installs the app on their organization.

Instance administrators can publish a custom app by the following procedure:

1. Go to **Administration > Apps**.
2. Find the custom app you want to publish and click **Detail**.
3. In the upper-right corner, click **Publish**.

{% hint style="info" %}
The **Share public link** and **Request approval** buttons replace **Publish**.
{% endhint %}

You can use the license parameter **installPublicApps** to control whether an organization can install an app developed in an external organization:

* **true** to permit installation
* `false` to deny installation **Default value**

## Approved app

Approving an app releases the app to all users and organizations on your instance. The custom app becomes one of your native apps and breaking changes are possible. Because of the accessibility and risks involved, be sure to test an app before approving it. Make tests all fields of all modules in scenarios before releasing an app.

### Approval flow

Once published, a user can submit their app for review and approval by clicking **Request approval**. The custom app then appears with a ✓ in the **In review** column of **Administration > Apps**.

To approve a custom app:

1. Go to **Administration > Apps**.
2. Find the custom app with a **✓** in the **In review** column and click **Details**.
3. In the upper-right corner, click **Approve**.
4. A popup appears prompting you to name the app. The name entered here is an internal identifier and does not appear in the user UI. Best practice is to delete any suffix. For example: `example-app` but not `example-app-abc123`
5. Click **Save**.

A small popup appears to confirm that the custom app was successfully compiled.

## Beta

You can mark custom apps as `beta` to indicate this status to all users. A beta label appears behind the app's name in all contexts: scenario builder, apps platform, and admin UI.

1. Go to **Administration > Apps**.
2. Find the custom app you want to publish and click **Detail**.
3. In the upper-right corner, click **Options**.
4. Click **Add beta label**.

The label now appears after the app's name on the same page and all other contexts.

You can remove the `beta` label by following the above procedure and clicking **Remove beta label** in step 4.
