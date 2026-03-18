# Migration of SSO

Creating a new custom domain impacts your SSO configuration. In this case, you need to migrate your SSO configuration to your new custom domain. The details of migrating your SSO depend on whether you have configured OAuth or SAML SSO.

### OAuth

If your identity provider (IdP) supports multiple OAuth redirect URIs, you only need to add the URI for your new Primary domain. Add your new Primary domain redirect URI before Make Infra/CloudOps configures your custom domain. No further action is required.

If your IdP only supports one OAuth redirect, you need to update this setting on your IdP after Make Infra/CloudOps configures your custom domain.

### SAML

After Make Infra/CloudOps configures your custom domain, you need to:

* Update your ACS and Entity Information settings on your IdP.
* Update your SSO settings on the System Settings page of the Administration interface of your Make White Label Instance.
* Generate and upload new certificates.

The migration process is similar to the procedure for when you first configure your [SAML SSO](../../manage-login/configure-single-sign-on/configure-single-sign-on-using-oauth-2.0-or-saml-2.0.md).
