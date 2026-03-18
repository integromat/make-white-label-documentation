# Install and configure apps

Make's administration interface lets you install, manage, and control access to apps on your instance. In order for your end-users to access apps in their scenarios, you must first install and configure them on your instance. Your instance has only several essential tools preinstalled by default. These preinstalled tools are necessary for all scenarios to execute and include important modules like routers, iterators, and aggregators. You need to install and configure any other app you want to provide on your instance.

Managing apps requires an instance-level role such as `SA` or `Admin`. Make organizes apps into two main groups, each with its own page in the admin interface:

* **Native Apps** - The complete catalog of apps that Make develops and publishes, including enterprise and premium apps. The Native apps page lets you:
  * [Install and configure native apps](native-apps/)
  * [Configure OAuth 2.0 connections required by some apps.](oauth-2.0-setup/)
* **Custom Apps** - Private apps that you or your end-users create. You can share access to custom apps in the following ways:
  * [Via a private link to restrict access to only those who have the link.](custom-apps/sharing-with-a-link.md)
  * [Via compiling the app to make the custom app available to all end-users.](custom-apps/compiling-the-app.md)
