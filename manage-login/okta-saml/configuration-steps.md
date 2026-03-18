# Configuration steps

Before configuring SSO, you need to assign a namespace and create a service provider certificate and private key. These important steps provide information you need to enter later.

Create your namespace:

1. Go to **Administration > System settings**.
2. Scroll down to **SSO Type**.
3. Under **SSO type**, select **SAML 2.0**.

Create your service provider primary key and certificate:

1. Use openssl or similar. Mac users can use Terminal
2. Enter the following command:

`openssl req -newkey rsa:2048 -new -nodes -x509 -keyout key.pem -out cert.pem`

This example creates two separate files:

* `key.pem`
* `cert.pem`

Locate these files and have them ready to upload later.
