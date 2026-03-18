# Base and primary domains

Make distinguishes between your Base and Primary domains.

### Base domain

A Base domain exists for all instances and has the URL `{{customName}}.onmake.com` or `{{customName}}.make.celonis.com` or similar.

Your Base domain:

* Always has our branding (i.e. xzy.onmake.com or xyz.make.celonis.com).
* Serves as alternative access in case of issues with your custom domain.
* Provides both public and admin interfaces.

### Primary domain

The Primary domain is the custom domain that you configure with Make's assistance.

* Your Primary domain:
* Is the custom domain that you define.
* Supports the availability of both public and administration interfaces.
* Can be the sender for email communications.
* Can be used as the SSO redirect URI.

{% hint style="warning" %}
In case of a problem with the primary domain, SSO login will not work.
{% endhint %}

* Appears in all dialogs in the interface, e.g. webhook creation, mailhook creation, etc.

