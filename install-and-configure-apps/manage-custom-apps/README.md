# Manage custom apps

You can allow your users to create custom apps by enabling the **Apps platform** option in **Administration > System Settings**. In the apps platform, your users can create apps that connect to third-party services not included in the apps developed and released by Make. The primary requirement is that the third party has an API. Refer to our public documentation for details on how to create a custom app.

Administrators can supervise custom app development and manage access to custom apps. Access to custom apps and their visibility to users varies according to the development stage. Each stage of custom app development corresponds to a status you can check by going to **Administration > Apps**. The following chart describes who can use a custom app in scenarios and how they access the custom app:

<table data-full-width="false"><thead><tr><th>Status</th><th>Creator</th><th>Creator's organization</th><th>All instance userts</th></tr></thead><tbody><tr><td>Private</td><td>Accesible</td><td>Only if installed by creator to the organization</td><td>Not accesible</td></tr><tr><td>Published</td><td>Accesible</td><td>Accesible</td><td>Only via a link from the creator</td></tr><tr><td>Approved</td><td>Accesible</td><td>Accesible</td><td>Accessible</td></tr></tbody></table>

