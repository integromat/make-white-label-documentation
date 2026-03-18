# Steps on Okta

1. Log in to Okta and go to **Admin > Applications > Applications**.
2. Click **Create app integration** and select **SAML 2.0**.
3. Name your app and upload your icon.
4. Click **Next**.
5. Configure the following SAML settings including:

| Setting                        | Description                  |
| ------------------------------ | ---------------------------- |
| Single sign-on URL             | 24.0.6                       |
| Audience URI (SP Entity ID)    | 1.28                         |
| Default RelayState             | Leave this field blank       |
| Name ID format                 | Select EmailAddress          |
| Application username           | Select **Okta username**     |
| Update application username on | Select **Create and update** |

6. Click **Show advanced settings** and enter the following:

| Setting                      | Description                                                                                                                                                                                                                                                                                                                                                                                                         |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Response                     | Select Signed                                                                                                                                                                                                                                                                                                                                                                                                       |
| Assertion signature          | Select Signed                                                                                                                                                                                                                                                                                                                                                                                                       |
| Signature algorithm          | Select RSA-SHA256                                                                                                                                                                                                                                                                                                                                                                                                   |
| Digest algorithm             | Select SHA256                                                                                                                                                                                                                                                                                                                                                                                                       |
| Assertion encryption         | <p>Select <strong>Unencrypted</strong></p><p></p><p>Optional:</p><p>If you want to encrypt assertions, you can select <strong>Encrypted</strong> and enter the following:</p><ul><li><strong>Encryption algorithm</strong>: AES256-CBC</li><li><strong>Key transport algorithm</strong>: RSA-OAEP</li><li><strong>Encryption certificate</strong>: Upload the <code>.pem</code> file you created earlier.</li></ul> |
| Signature certificate        | Upload a `.pem` file of the Service Provider Certificate. You need to also upload this to the Service Provider Certificate field of your Make SSO configuration tab. These two certificates must be the same for your SSO implementation to work successfully.                                                                                                                                                      |
| Enable Single Logout         | Leave unchecked                                                                                                                                                                                                                                                                                                                                                                                                     |
| Signed requests              | Optional                                                                                                                                                                                                                                                                                                                                                                                                            |
| Other requestable SSO URLs   | Optional                                                                                                                                                                                                                                                                                                                                                                                                            |
| Assertion inline hook        | Select **None (disable)**                                                                                                                                                                                                                                                                                                                                                                                           |
| Authentication context class | Select **PasswordProtectedTransport**                                                                                                                                                                                                                                                                                                                                                                               |
| Honor force authentication   | Select **Yes**                                                                                                                                                                                                                                                                                                                                                                                                      |
| SAML issuer ID               | http://www.okta.com/${org.externalKey}                                                                                                                                                                                                                                                                                                                                                                              |

7. Enter the following attributes and click **Next**.

| Name             | Name format | Value      |
| ---------------- | ----------- | ---------- |
| profileFirstName | Unspecified | 24.0.6     |
| profileLastName  | Unspecified | 1.28       |
| email            | Unspecified | user.email |

8. In the **Are you a customer or partner?** field, select **I'm an Okta customer adding an internal app.**
9. In the **App type** field, select **This is an internal app that we have created**
10. Click **Finish.**

### To locate your IdP login URL and certificate:

1. Go to **Admin > Applications > Applications** and select your SAML SSO app. to access the necessary information.
2. Go to the **Sign on** tab and click **View SAML setup instructions.**
