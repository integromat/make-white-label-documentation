# Custom code injection

The **Custom code** tab of **Administration > System settings** lets you inject your custom code into any customer-facing `html` in the following places:

* The header
* The footer

You can inject a custom code to customize the appearance of your Make White Label and integrate it with third parties such as Zendesk and HotJar.

Each field has a character limit of 5,000 characters. If you use externally loaded content or third-party integrations such as Hotjar, Segment, or Google Tag Manager, you need to update the [Dynamic CSPs](dynamic-csps.md) with the relevant URLs.

Because adding custom codes risks irreversible damage to your instance, use the following procedure to identify possible issues and address them first:

1. Use the Dynamic CSPs field to allow resources and content from the external URLs in your custom HTML. See the section on [Dynamic CSPs below for details](dynamic-csps.md).

{% hint style="info" %}
Third parties have support documentation for the CSPs required by your custom code.
{% endhint %}

2. In a Chrome browser window, load a page on your white-label instance where you want to see your changes.
3. Right-click on any element on your instance's page and select **Inspect**.
4. In the developer console, find the **Console** section. Copy-paste the section of your code between `<script>` and `</script>`, and hit **Enter**.
5. The console displays information about any errors. If there are no errors, you can see your changes live in your browser as a temporary preview.

{% hint style="info" %}
The console identifies errors related to your CSP. In this case, update your Dynamic CSPs and click Save.
{% endhint %}

6. Optional: For custom footers, right-click in the Elements section and select Edit as HTML. Find `<body>` and copy-paste your custom footer before `</body>`.
7. Check that your changes both look and function properly in your browser

Your browser displays a preview of your integrated custom code. If your preview does not appear correct, use the information in the **Console** section to troubleshoot.

***

If the above procedure loads your custom code without issues, use the following procedure to insert your custom code:

1. Go to **Administration > System settings**.
2. Find **Code Injections**.
3. In the **Header** field, enter the code you want injected into the `<header>` section of user-facing HTML.
4. In the **Footer** field, enter the code you want injected before `<before>` in user-facing HTML.
5. Click **Publish**.

Your changes go live within 10 minutes and apply to the administration UI as well as the customer-facing UI.

Most common problems involve CSPs. Edit your **Dynamic CSPs** based on the errors you find in the developer tools.
