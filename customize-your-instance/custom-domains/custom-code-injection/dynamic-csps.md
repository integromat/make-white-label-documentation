# Dynamic CSPs

The Dynamic CSPs field of **System settings** lets you customize your instance's Content Security Policy (CSP). To permit resources and content from external URLs, use the following procedure:

1.  Create a JSON array of the permitted sources. You can use CSP directives as the key and domains as the value according to the following format:

    1. Omit the dash and any characters after the dash of a CSP directive. Examples: `connect` for `connect-src` or `font` for `font-src`
    2. Omit `https://` from URLs. You can use wildcards. Examples: `drive.example.com` or \*.example.com
    3. Example JSON array:

    { "connect": \[<mark style="color:green;">".example.com"</mark>, <mark style="color:green;">"wss://web.socket.com"</mark>], "font": \[<mark style="color:green;">".example.com"</mark>] }

{% hint style="info" %}
For WebSockets, you must include `wss://`
{% endhint %}

2. Insert your JSON object into the **Dynamic CSPs** field.
3. Click **Save**.

A message briefly appears confirming the changes are saved.
