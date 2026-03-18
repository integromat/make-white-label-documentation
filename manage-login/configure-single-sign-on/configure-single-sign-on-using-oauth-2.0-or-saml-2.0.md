# Configure single sign-on using OAuth 2.0 or SAML 2.0

{% hint style="warning" %}
Double-check your SSO configuration before you click Save on the SSO settings page. When you click Save, Make enables SSO with the settings you provided. and logs you out immediately. You cannot log in with your credentials anymore.
{% endhint %}

1. Log in to your Make White Label instance.
2. Go to **Administration > System settings**.
3. Select an SSO type.
   1. **None** - default option indicating that SSO is turned off.
   2. **OAuth 2.0**
      1. Select this option for OpenID Connect (OIDC).
   3. **SAML**
4. Fill in the protocol-specific information as described in the tables following this procedure.
5. Enter an IML resolve. The IML resolve maps necessary data such as ID, name, and email, between Make and your identity provider.
6. Under SSO Options, define whether and how your instance assigns new users to organizations. You can choose from the following options:
   * Don't create a new organization.
     * This option only creates a new user. That new user has no access to the scenario editor or other features. You must manually add the new user to an organization.
   * Create a new organization and team.
     * This option is similar to what happens to Make users on the public cloud. They receive their own organization and can create scenarios as they like.
   * Assign to an existing organization and team.
     * This option requires entering the organization ID number and team ID number. An example use case is users within the same company. Each new user joins the organization and can only access their assigned organization and team.
7. Click **Save**.

{% hint style="info" %}
If you do not select a default team, users logging in through SSO will not be able to access any data. This is because all types of data within Make must belong to a team. If a user does not belong to any teams, they cannot work with Make . [Read more about teams](https://www.make.com/en/help/access-management/teams).
{% endhint %}

Make enables SSO with the settings you provided and logs you out immediately. You can now log in with your SSO provider credentials. At the same time, you receive an email with a one-time link, which you can click to disable SSO. Use the one-time link within 24 hours before it expires. After 24 hours you must contact your customer success specialist.

{% hint style="info" %}
When logging in using SSO for the first time, you must use an account that has the same email address as the account that you used to configure SSO. Make sure that you assign the same email address to the user in your identity provider.
{% endhint %}

### Open ID Connect (OAuth 2.0 settings)

The following fields appear once you select OAuth 2.0 from the SSO menu:

<table><thead><tr><th width="208">Field</th><th width="107">Required</th><th>Description</th></tr></thead><tbody><tr><td>User Information URL</td><td>Yes</td><td><p>URL obtained from your identity provider.</p><p>Example: <code>https://example.com/oauth2/v1/userinfo</code></p></td></tr><tr><td>Client ID</td><td>Yes</td><td>Obtained from your identity provider. Sometimes called Application ID.</td></tr><tr><td>Token URL</td><td>Yes</td><td><p>required</p><p>URL obtained from your identity provider.</p><p>Example: <code>https://example.com/oauth2/v1/token</code></p></td></tr><tr><td>Login scopes</td><td>optional</td><td>Parameters used when accessing your identity provider.</td></tr><tr><td>Scopes separator</td><td>optional</td><td>The character used between scopes, such as a space or a comma. If your separator is a space, use the spacebar on your keyboard.</td></tr><tr><td>Authorize URL</td><td>Yes</td><td><p>URL obtained from your identity provider.</p><p>Example: <code>https://example.com/oauth2/v1/authorize</code></p></td></tr><tr><td>Client secret</td><td>Yes</td><td>Obtained from your identity provider.</td></tr><tr><td>IML resolve</td><td>Yes</td><td><p>Because both Make and your Identity provider use attributes such as username and email, you need to map these attributes using IML.</p><p></p><p>For Open ID Connect:</p><p><code>{"id":"{{sub}}","email":"{{email}}","name":"{{name}}"}</code></p></td></tr><tr><td>Redirect URL</td><td>optional</td><td>The location where the identity provider sends the user once successfully authorized and granted access. Must be unique to your application/instance.</td></tr></tbody></table>

### SAML 2.0 settings

<table><thead><tr><th width="249">Field</th><th width="116">Required</th><th>Description</th></tr></thead><tbody><tr><td>Service provider primary key</td><td>Yes</td><td><p>The private key used to sign requests. You can get this from your certificate authority or create your primary key using OpenSSL. Make can extract this from the following file formats:</p><ul><li>P12</li><li>PFX</li><li>PEM</li></ul></td></tr><tr><td>Service provider certificate</td><td>Yes</td><td><p>An x.509 certificate you create. Make can extract this from the following file formats:</p><ul><li>P12</li><li>PFX</li><li>PEM</li></ul></td></tr><tr><td>Identity provider certificate</td><td>Yes</td><td><p>An x.509 certificate created and stored by your IdP, for example, Google, Okta, or Microsoft Azure Directory. You can enter this information in the following ways:</p><ul><li>Copy and paste from your IdP's UI.</li><li>Copy and paste from your IdP's metadata XML file.</li><li><p>Extract from any of the following:</p><ul><li>P12</li><li>PFX</li><li>PEM</li></ul></li></ul></td></tr><tr><td>IdP login URL</td><td>Yes</td><td>Also called an authorization URL. The IdP login URL is available from your IdP, for example, Google, or Okta. The IdP metadata typically contains this information in XML. The IdP metadata is usually downloadable from your Identity provider.</td></tr><tr><td>IdP logout URL</td><td>Yes</td><td>A URL created by your IdP to enable Single Log Out (SLO). Leave this field empty to disable SLO.</td></tr><tr><td>Login IML resolve</td><td>Yes</td><td>Because both Make and your Identity provider use attributes such as username and email, you need to map these attributes using IML.</td></tr><tr><td>Redirect URL</td><td>Optional</td><td>The location where the identity provider sends the user once successfully authorized and granted access. Must be unique to your application/instance.</td></tr><tr><td>Allow unencrypted assertions</td><td>Optional</td><td>Your IdP may not support SAML 2.0 assertions with encryption. Check with your IdP to determine whether you need to enable this option.</td></tr><tr><td>Allow unsigned responses</td><td>Optional</td><td>Your IdP may not support a signed SAML 2.0 response. Check with your IdP to determine whether you need to enable this option.</td></tr><tr><td>Sign requests</td><td>Optional</td><td>Your IdP may require a signed SAML 2.0 response. Check with your IdP to determine whether you need to enable this option.</td></tr><tr><td>Audience</td><td>Optional</td><td>Optional field to define the intended target. Typically this is a URL but can also be formatted as any string of data.</td></tr></tbody></table>

### Create your service provider primary key and certificate

Your Make White Label instance signs and verifies SAML 2.0 requests with the primary key and certificate that you provide.

Use `openssl` or similar as in the following example:

`openssl req -newkey rsa:2048 -new -nodes -x509 -keyout key.pem -out cert.pem`

This example creates two separate files that you can extract into the following fields:

* Service provider primary key
* Service provider certificate

### Create URLs for your instance as a service provider

To configure SSO on your identity provider, you need to provide URLs. The following are examples using the base domain `https://example.celonis.integromat`.

Adjust them according to the domain of your instance.

* SAML ACS URL: `https://example.celonis.integromat.com/sso/saml`
* SAML Entity Information URL (also known as Audience Restriction URL): `https://example.celonis.integromat.com/sso/saml`

### Create and enter Login IML resolve

To support a broad choice of identity providers (IdPs), Make lets you map values related to identifying users. The IML resolve maps the values from your IdP to Make's internal values by using IML, a JavaScript-based function notation. Your IML resolve must be specific to your IdP. You must map the following properties:

| Field   | Description                                                                                                                                                                                              |
| ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `email` | <p>You can map this to any valid email.</p><p></p><p><strong>Note</strong>: Aliases and alternate email suffixes can create problems. Be sure to map the most appropriate email in your IML resolve.</p> |
| `name`  | <p>Used as the user's name in the application.</p><p>You can reuse email for this property.</p><p>If left blank creates a user without a name that must be updated later.</p>                            |
| `id`    | <p>External user ID</p><p>Can be an <code>integer</code> or <code>string</code> but must be mapped to an identifier.</p>                                                                                 |

### Example

In the following example, the resolve maps the following values:

```json
{
"email":"{{get(user.attributes.email, 1)}}",
"name":"{{get(user.attributes.firstName, 1)}} {{get(user.attributes.last}}
"id":"{{user.name_id}}"
}
```
