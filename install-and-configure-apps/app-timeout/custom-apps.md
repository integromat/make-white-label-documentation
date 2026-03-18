---
description: For custom apps, you can add a timeout parameter in the app's configuration.
---

# Custom Apps

To change the timeout of a custom app:

1. Go to the **Apps** page and click **Detail** for the app you want to edit.
2. Go to the **Base** tab.
3. Add or change the timeout in the app's **Common data** field by entering the following parameter with time in milliseconds: `{"timeout":300000}`
4. Click the save icon.

{% hint style="warning" %}
The maximum timeout value is 300,000 milliseconds.
{% endhint %}

The page validates and saves your updated timeout. You can view this information in the **Common data** field.
