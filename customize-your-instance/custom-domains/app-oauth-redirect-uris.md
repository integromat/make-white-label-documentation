# App OAuth redirect URIs

For OAuth connections, such as Facebook apps, for example, you can use only one domain for redirect URIs. You can use either your Base or Primary domain as the redirect URI but not both. Best practice is to begin this process before Make completes your custom domain. Because most OAuth 2.0 connections support at least 2 redirect URIs, you can add the new redirects before your custom domain is active without impacting scenarios on your instance.

Example: Your Base domain is `xyz.onmake.com` and your new Primary domain is `customdomain.com`. You can use either `xyz.onmake.com` or `customdomain.com`. You cannot use both.

{% hint style="warning" %}
If the third party requires domain verification, such as Google and Microsoft, you need to use your primary domain.
{% endhint %}

You need to update your OAuth apps on the third-party side if you decide to change their configuration to your new Primary domain.

Example: You have a Facebook OAuth 2.0 configuration that uses your Base domain, `xyz.onmake.com`. If you want to change this configuration to your new Primary domain, `customdomain.xyz.com`, you need to manually update the redirect URIs at the Meta developers portal.

{% hint style="info" %}
We recommend that you begin the migration process before we complete your custom domain. Once you decide on your custom domain, you can add `/oauth/cb/{{appInternalName}}`.

Examples:

`https://yourcustomdomain.com/oauth/cb/google`\
`https://yourcustomdomain.com/oauth/cb/google-restricted`\
`https://yourcustomdomain.com/oauth/cb/facebook`
{% endhint %}

