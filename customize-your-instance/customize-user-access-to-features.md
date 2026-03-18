# Customize user access to features

You can configure user access to your Make White Label instance and features on the Administration > System Settings page.

### Instance access

#### Two-factor authentication

Two-factor authentication defines user access to two-factor authentication on your White Label instance.

* **Enable** to allow users to configure two-factor authentication.
* **Disable** to turn off two-factor authentication. Recommended if you configure SSO for your instance.

For Two factor authentication app name (visible in Google Authentificator), you need to enter the name you want to appear in the Google Authentificator app.

#### SSO

You can use this field to select the kind of SSO you want to configure on your Make White Label instance.

### Feature access

The following options define access on an instance-wide level.

To allow your users access to a feature, you need to enable it for your instance and then use the license object to allow organizations to access to that specific feature.

For example, to offer custom functions:

1. Enable **Custom Functions** on **Administration > System settings** by selecting **Enabled** under **Custom Functions**.
2. Include `customFunctions: true` in the organization's license object for each organization you want to have access to custom functions.

Any organization with `customFunctions: true` in its license can use the custom functions feature.

<table><thead><tr><th width="169">Feature</th><th>How enable for your instance</th><th>Relevant license parameter</th></tr></thead><tbody><tr><td><strong>Devices enabled</strong></td><td>This feature does not impact your instance or its users. Keep this parameter set to <code>disabled</code>.</td><td>Not applicable</td></tr><tr><td><strong>Apps platform</strong></td><td><p>Defines whether users can create their own custom apps.</p><p><strong>Enable</strong> to allow access on your instance.</p><p><strong>Disable</strong> to turn off the feature for your instance.</p></td><td>There is no license parameter. Selecting <strong>Enable</strong> allows all of your users to access the apps platform and create custom apps.</td></tr><tr><td><strong>Custom Functions</strong></td><td><p>Defines whether users can use <a href="https://www.make.com/en/help/functions/custom-functions">custom functions</a> in their organizations.</p><p><strong>Enable</strong> to allow access on your instance.</p><p><strong>Disable</strong> to turn off the feature for your instance.</p></td><td><p><code>customFunctions</code></p><p><strong>Boolean</strong></p><p><strong>True</strong> to allow an organization to use custom functions.</p><p><strong>False</strong> to prevent an organization from using custom function.</p></td></tr><tr><td><strong>Variables</strong></td><td><p>Defines whether users can use <a href="https://www.make.com/en/help/functions/variables#custom-variables-1529751">custom variables</a> in their organizations.</p><p><strong>Enable</strong> to allow access on your instance.</p><p><strong>Disable</strong> to turn off the feature for your instance.</p></td><td><p><code>customVariables</code></p><p><strong>Boolean</strong></p><p><strong>True</strong> to allow an organization to use custom variables.</p><p><strong>False</strong> to prevent an organization from using custom variables.</p></td></tr><tr><td><strong>Dynamic connections</strong></td><td><p>Defines whether users can use <a href="https://www.make.com/en/help/connections/dynamic-connections">dynamic connections</a> in their scenarios.</p><p><strong>Enable</strong> to allow access on your instance.</p><p><strong>Disable</strong> to turn off the feature for your instance.</p></td><td><p><code>dynamicDependencies</code></p><p><strong>Boolean</strong></p><p><strong>True</strong> to allow an organization to use dynamic dependencies in scenarios.</p><p><strong>False</strong> to prevent an organization from using dynamic dependencies in scenarios.</p><p></p><p><code>dynamicConnections</code></p><p><strong>Boolean</strong></p><p><strong>True</strong> to allow an organization to use dynamic connections in scenario inputs and map them in modules.</p><p><strong>False</strong> to prevent an organization from using dynamic connections in scenario inputs and mapping them in modules.</p></td></tr><tr><td><strong>Personal connections</strong></td><td>This feature does not impact your instance or its users. Keep this parameter set to <code>disabled</code>.</td><td>Not applicable</td></tr><tr><td><strong>On Prem Agent</strong></td><td>This feature does not impact your instance or its users. Keep this parameter set to <code>disabled</code>.</td><td>Not applicable</td></tr><tr><td><strong>Scenario inputs</strong></td><td><p>Defines whether users can use <a href="https://www.make.com/en/help/scenarios/scenario-inputs">scenario inputs</a> in their scenarios.</p><p><strong>Enable</strong> to allow access on your instance.</p><p><strong>Disable</strong> to turn off the feature for your instance.</p></td><td><p><code>scenarioIO</code></p><p><strong>Boolean</strong></p><p><strong>True</strong> to allow an organization to use scenario inputs.</p><p><strong>False</strong> to prevent an organization from using scenario inputs.</p></td></tr><tr><td><strong>Users can create organizations</strong></td><td>This feature does not impact your instance or its users. Keep this parameter set to <code>disabled</code>.</td><td>Not applicable</td></tr><tr><td><strong>Custom scenario properties</strong></td><td><p>Defines whether users can use custom scenario properties in their organizations.</p><p><strong>Enable</strong> to allow access on your instance.</p><p><strong>Disable</strong> to turn off the feature for your instance.</p></td><td><p><code>customProperties</code></p><p><strong>Integer</strong></p><p><code>0</code> to disable custom scenario properties for an organization.</p><p><code>1</code> or higher to define the number of custom scenario properties an organization can create.</p></td></tr></tbody></table>

### Maintenance mode

Maintenance mode displays a screen that explains to your users that they cannot access your instance due to the maintenance activity on your instance. You can enable maintenance mode and customize the message to your users from the System settings page.

1. Go to **Administration > System Settings**.
2. Scroll down to the **Maintenance mode** field.
3. Select **Enabled**.
4. Enter the custom message you want your users to see on the maintenance mode screen.
5. Click **Save** in the lower right corner.

A green notification appears briefly to confirm the changes are saved.
