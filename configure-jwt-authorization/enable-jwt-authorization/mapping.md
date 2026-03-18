# Mapping

To enable JWT authorization to perform the above tasks, you need to map the values of your JWT payload so your instance can extract the relevant data.

You can map the decrypted JWT content by using the `payload` keyword. Also, `body`, `headers`, and `query` are available for mapping via the corresponding keywords.

In the configuration field, you need to map your values using IML, a templating language used by Make. You can use the following pattern:

`{{payload.yourParameterName}}`

The following are examples of IML mapping for the fields in the JWT configuration section:

### User

| Name       | Description                                                                                                                                              |
| ---------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| externalID | \{{payload.userId\}}                                                                                                                                     |
| email      | \{{payload.userEmail\}}                                                                                                                                  |
| name       | \{{payload.userName\}}                                                                                                                                   |
| country    | <p>{{payload.country}}</p><p>Note: Countries must conform to <a href="https://en.wikipedia.org/wiki/ISO_3166-1_alpha-3">ISO 3166-1</a>.</p>              |
| timezone   | <p>{{payload.tz}}</p><p>Note: Time zones must conform to the <a href="https://en.wikipedia.org/wiki/List_of_tz_database_time_zones">tz database</a>.</p> |
| locale     | \{{payload.userLocale\}}                                                                                                                                 |
| language   | \{{payload.lang\}}                                                                                                                                       |

### Organization

| Name       | Description                  |
| ---------- | ---------------------------- |
| externalId | \{{payload.organizationId\}} |
| name       | \{{payload.orgName\}}        |
| timezone   | \{{payload.orgName\}}        |
| timezone   | \{{payload.tz\}}             |

### Team

| Name       | Description            |
| ---------- | ---------------------- |
| externalId | \{{payload.teamId\}}   |
| name       | \{{payload.teamName\}} |

The following are examples of IML mapping for the fields in the JWT configuration section:

### Custom contexts

In case you need to provide custom context to RPCs and Accounts based on the JWT token payload, you can add context keys. Once mapped, the context is then available as `environment.context` in AccountWorkers and RPCWorkers. You map values with [IML](https://app.gitbook.com/s/NS0mCBwODiYtOVXjc6qf/block-elements/iml) the same way for custom contexts as you did for users, organizations, and teams. See the [example of a custom base domain](mapping.md#example-a-custom-base-domain) following the procedure.

The following procedure creates a custom context:

1. Click **+ Add item**.
2. In the **property** field, enter the internal Make parameter you want to map.
3. In the **value** field, map the payload parameter value you want extracted.
4. Click **Save** in the lower right corner.

Your custom context is now available as `environment.context` in AccountWorkers and RPCWorkers.

### Example: A custom base domain

In this example, your JWT payload contains a custom base domain that you need for creating new accounts.

```json
{
"userId": "123456789",
"userEmail": "myemail@email.com",
"organizationId": "XYZ123",
"teamId": "DEF45G",
"tz": "Europe/Prague",
"customBaseDomain": "organization.integromat.cloud" // This is the parameter you want to map.
}
```

Use the following property and value to map the custom base domain:

* property: `teamdomain`
* value: `{{payload.customBaseDomain}}`
