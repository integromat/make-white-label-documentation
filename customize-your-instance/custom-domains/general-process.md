# General process

We perform the necessary with the minimum downtime of scenario processing with minimal impact on scenarios, webhooks, and mailhooks. The following is a description of the process for creating a custom domain:

1. You confirm that you can log into the instance administration.
2. Make provides you with NS configuration instructions.
3. You set the DNS NS records according to Make's instructions.
4. Make switches your instance to maintenance mode.
5. You are responsible for any required SSO migration.
6. Make performs the following to configure the custom domain and facilitate migration:
   * Creates:
     * new SSL certificates and sets up renewal automation
     * the Name Server
   * Regenerates DNS records (current TTL is 300 sec).
   * Configures new nginx proxy rules to access:
     * Public interfaces, admin interfaces, and webhooks on base and primary domains
     * API on all domains
   * Reconfigures:
     * the new primary domain address for all services
     * HTTP proxy
     * LetsEncrypt for your custom domain
     * particular application services for your custom domain
     * the mail server to support DKIM signing for your custom domain
7. You are responsible for any required SSO reconfiguration.
8. Make switches off maintenance mode.
