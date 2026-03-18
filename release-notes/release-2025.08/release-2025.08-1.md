# Release 2025.08-1

### Updated service version

This **hotfix** updates the `roleman` service. It includes a security fix related to database SSL certificates and introduces support for custom Docker image naming.

<table><thead><tr><th width="275.338623046875">Service</th><th>Version number</th></tr></thead><tbody><tr><td>roleman</td><td>2026.03.09-f0bcc2a</td></tr></tbody></table>

### Critical security fix: **Database SSL certificate handling**

We've resolved a vulnerability that could result in the unintended exposure or leaking of SSL certificates used for database connections. This update secures database connection strings and prevents certificate leakage.

### Enhancement: Custom Docker image naming

We've added support for custom Docker image naming. You can now configure image names to align with your internal container registries and deployment pipelines, as requested by our community.
