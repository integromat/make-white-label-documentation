# Configure the module Email > Send an Email to a Team Member

The native app **Email** includes a module **Send an Email to a Team Member** that users can put in their scenarios that automatically sends the specified person an email with a custom subject and body. To offer this module, you need to add the following parameters in JSON in the **Email** app's common data. The `from` object lets you define the user and email address your users receive these emails from.

1. Go to **Administration > Native Apps**.
2. Click **Email**.
3. Click the **App: 7.3.19** tab.
4. Click the toggle for **Send an Email to a Team Member** to make it visible and accessible for your users.
5. In the **Common data** field, create an enter a JSON object using the parameters and example below.
6. Click the **save icon** to save your changes.

<table><thead><tr><th width="172">Parameter</th><th width="96">Required</th><th width="119">Data type</th><th>Description</th></tr></thead><tbody><tr><td>maxPastRecords</td><td>-</td><td>integer</td><td><p>Defines the maximum number of emails retrieved in the "Choose where to start - Select the first email" action.</p><p></p><p>Default: 120</p><p>Maximum: 121</p></td></tr><tr><td>timeout</td><td>-</td><td>integer</td><td><p>Defines the connection timeout in milliseconds.</p><p>Default: 30000</p></td></tr><tr><td>smtp</td><td>Yes</td><td>object</td><td>Defines the SMTP connection settings for sending emails.</td></tr><tr><td>port</td><td>Yes</td><td>integer</td><td>Defines the SMTP port for sending emails.</td></tr><tr><td>host</td><td>Yes</td><td>string</td><td>Defines the host domain for sending emails.</td></tr><tr><td>secure</td><td>Yes</td><td>booelan</td><td>Defines whether SMTP requires secure encryption.</td></tr><tr><td>authMethod</td><td>Yes</td><td>string</td><td>Defines the SMTP authentication method.</td></tr><tr><td>auth</td><td>Yes</td><td>object</td><td>An objection containing the credentials for sending emails.</td></tr><tr><td>user</td><td>Yes</td><td>string</td><td>The username for sending emails.</td></tr><tr><td>password</td><td>Yes</td><td>string</td><td>The password for sending emails.</td></tr><tr><td>from</td><td>Yes</td><td>string</td><td>The name and email address that your users will see as the sender of these emails.</td></tr><tr><td>template</td><td>-</td><td>string</td><td><p>The public URL of an HTML template you want to use for the emails sent to users. The user-defined content of the email message replaces the {{body}} placeholder.</p><p>Default: a Make template</p></td></tr></tbody></table>

```json
{"maxPastRecords":100,"timeout":60000,"smtp":
{"port":"465","host":"smtp.domain.com","secure":true,"authMethod":"PLAIN","auth":
{"user":"user@mydomain.com","pass":"NOTp@55w0rd!"}},"from":"A. N. Example at Company a.n.example@company.com"}
```

