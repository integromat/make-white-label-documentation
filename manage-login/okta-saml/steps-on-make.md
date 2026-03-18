# Steps on Make

1. Go to **Organization > SSO**.
2. Enter the following information from Okta into the IdP login URL and Identity provider certificate fields.

```html
{"email":"{{get(user.attributes.email, 1)}}","name":"{{get(user.attributes.profileFirstName, 1)}}
{{get(user.attributes.profileLastName, 1)}}","id":"{{user.name_id}}"}
```

3. In the **Allow unencrypted assertions**, select **Yes**.
4. In the **Allow unsigned responses**, select **No**.
5. To allow the **Sign requests**, select **Yes**.
6. Click **Save**.
