# Versioning and maintenance

Over time, you or your users might need to make changes to or new versions of a custom app. The process varies depending on the publishing status. Private and public apps share the same process that can result in [breaking changes](https://app.gitbook.com/s/NS0mCBwODiYtOVXjc6qf/app-maintenance/updating-your-app/approved-apps/managing-breaking-changes). Approved apps have a separate process and can only experience breaking changes when the changes are compiled.

A key difference between changes in private/public apps compared to approved apps is when and how changes take effect. Any changes to a private or public app apply immediately. As a result, breaking changes are more likely to occur. Proceed with caution when changing a private or public app's code. See the [public documentation on breaking changes](https://app.gitbook.com/s/NS0mCBwODiYtOVXjc6qf/app-maintenance/updating-your-app/approved-apps/managing-breaking-changes) for details.

Changes to an approved app require administrative approval before taking effect for instance users. Besides minimizing risk to your instance, there is another advantage. The user who created and developed the custom app has access to a private version of their app after an administrator approves the app. This user is able to make changes and test them using this private version before requesting admin approval.

When there are significant changes to the existing API or new API version, it may be best to create a new version of the app. When deciding whether to update the current app or create a new app version, take into account the user experience. Updating tens or hundreds of scenarios might be complicated and a time-consuming process. If possible, prioritize updating the current app instead of creating a new version.

### Private/public apps

#### Changes and updates

{% hint style="warning" %}
The risk of breaking changes in private and public apps is greater compared to approved apps. All changes take effect immediately for private and public apps.
{% endhint %}

In custom apps that haven't been approved, it is not possible to keep track of changes as there is no version control tool available.

If you need to keep track of changes and there is no plan to have the app approved, you can use the VS Code extension to export the current version of the app every time you make a change and store the files on GitHub or any similar tool.

{% hint style="warning" %}
Ensure there are no Javascript **syntax warnings or errors** on the custom IML functions in the app. Otherwise, all scenarios that are using the app throw an error message about Javascript syntax and then stop executing immediately.

This affects all scenarios that contain any module of the custom app causing the Javascript error.
{% endhint %}

### Versioning

If you find out that a new API version has been implemented, or there have been major changes in the current API made, the best practice is to create a new app.

This way, everything stays consistent and there are no breaking changes made in the current app.

### Approved apps

#### Changes and upates

Once you as an administrator approve an app, the code is locked and it starts to be versioned. When a new change is made in the code of the app, it automatically creates diff files, which contain detailed information about the changes. Every change made to the app is visible only to the user developing it unless an administrator commits the changes. Users developing apps can safely add and test new functions and when they are stable, they can have the changes checked by you and released on the instance level. Diff files are available in both environments, the web interface, and VS Code extension. Always make sure the changes will not break existing scenarios.

You can compile changes to an approved custom app:

1. Go to **Administration > System settings** and click **Detail** for the app you want to update.
2. Review the changes in the code by going to the **Changes** tab and clicking the icon for changes that appear there.
3. A redirect takes you to the relevant tab. In the yellow banner, click Show diff.

The changes appear in two columns that use red and green to highlight changes.

#### Versioning

{% hint style="warning" %}
If possible, prioritize updating an approved app instead of creating a new version. New versions require manual changes to each scenario that uses an approved app. Because of these user experience considerations, the best practice is to update an approved app rather than create new versions.
{% endhint %}

Creating a new app version is best practice only in the following cases:

* There are major changes in the current API. For example, significant changes that impact the functionality of multiple modules.
* There is a new API version available. For example, a change from REST-style API to GraphQL-style.
* It is not possible to update the current app without [breaking changes](https://app.gitbook.com/s/NS0mCBwODiYtOVXjc6qf/app-maintenance/updating-your-app/approved-apps/managing-breaking-changes).

Following these guidelines ensures a consistent user experience and that there are no breaking changes. If you decide to release a new version, users need to upgrade the modules in their scenarios using our [upgrade module tool](https://www.make.com/en/help/modules/replacing-legacy-modules-with-new-modules).
