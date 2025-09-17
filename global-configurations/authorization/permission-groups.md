# Permission Groups

Using the `Permission groups`, you can assign a user to a particular group and a user inherits all the permissions granted to the group.

The advantage of the `Permission groups` is to define a set of privileges like create, edit, or delete for the given set of resources that can be shared among the users within the group.

{% hint style="info" %}
The [User permissions](user-access.md) section for `Specific permissions` contains a drop-down list of all existing groups for which a user has an access. This is an optional field and more than one groups can be selected for a user.
{% endhint %}

## Add Group

Go to **Global Configurations** → **Authorization** → **Permissions groups** → **Add group**.

![](https://devtron-public-asset.s3.us-east-2.amazonaws.com/images/global-configurations/permission-group/permission-group-1.jpg)

Enter the `Group Name` and `Description`.

![](https://devtron-public-asset.s3.us-east-2.amazonaws.com/images/global-configurations/permission-group/permission-group-2.jpg)

You can either grant [super-admin](user-access.md#role-based-access-levels) permission to a user group or specific permissions to manage access for:

* [Devtron Apps](permission-groups.md#devtron-apps-permissions)
* [Helm Apps](permission-groups.md#helm-apps-permissions)
* [Jobs](permission-groups.md#jobs)
* [Kubernetes Resources](permission-groups.md#kubernetes-resources-permissions)
* [Chart Groups](permission-groups.md#chart-group-permissions)

### Devtron Apps Permissions

In `Devtron Apps` option, you can provide access to a group to manage permission for custom apps created using Devtron.

{% hint style="info" %}
The `Devtron Apps` option will be available only if you install [CI/CD integration](../../usage/integrations/build-and-deploy-ci-cd.md).
{% endhint %}

Provide the information in the following fields:

![](https://devtron-public-asset.s3.us-east-2.amazonaws.com/images/global-configurations/permission-group/permission-group-devtron-apps-v2.jpg)

| Dropdown        | Description                                                                                                                                                                                                                                                                                                                           |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Project**     | <p>Select a project from the drop-down list to which you want to give permission to the group. You can select only one project at a time.<br>Note: If you want to select more than one project, then click <code>Add row</code>.<br></p>                                                                                              |
| **Environment** | <p>Select the specific environment or all environments from the drop-down list.<br>Note: If you select <code>All environments</code> option, then a user gets access to all the current environments including any new environment which gets associated with the application later.<br></p>                                          |
| **Application** | <p>Select the specific applications or all applications from the drop-down list corresponding to your selected Environments.<br>Note: If you select <code>All applications</code> option, then a user gets access to all the current applications including any new application which gets associated with the project later<br>.</p> |
| **Role**        | <p>Select one of the <a href="permission-groups.md#role-based-access-levels">roles</a> to which you want to give permission to the user:</p><ul><li><code>View only</code></li></ul><ul><li><code>Build and Deploy</code></li></ul><ul><li><code>Admin</code></li></ul><ul><li><code>Manager</code></li></ul>                         |

You can add multiple rows for `Devtron Apps` permission.

Once you have finished assigning the appropriate permissions for the groups, Click **Save**.

### Helm Apps Permissions

In `Helm Apps` option, you can provide access to a group to manage permission for Helm apps deployed from Devtron or outside Devtron.

Provide the information in the following fields:

![](https://devtron-public-asset.s3.us-east-2.amazonaws.com/images/global-configurations/permission-group/permission-groups-helm-apps-v2.jpg)

| Dropdown                             | Description                                                                                                                                                                                                                                                                                                                                                                |
| ------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Project**                          | <p>Select a project from the drop-down list to which you want to give permission to the group. You can select only one project at a time.<br>Note: If you want to select more than one project, then click <code>Add row</code>.<br></p>                                                                                                                                   |
| **Environment or cluster/namespace** | <p>Select the specific environment or <code>all existing environments in default cluster</code> from the drop-down list.<br>Note: If you select <code>all existing + future environments in default cluster</code> option, then a user gets access to all the current environments including any new environment which gets associated with the application later.<br></p> |
| **Application**                      | <p>Select the specific application or all applications from the drop-down list corresponding to your selected Environments.<br>Note: If <code>All applications</code> option is selected, then a user gets access to all the current applications including any new application which gets associated with the project later<br>.</p>                                      |
| **Role**                             | <p>Select one of the <a href="permission-groups.md#role-based-access-levels">roles</a> to which you want to give permission to the user:</p><ul><li><code>View only</code></li></ul><ul><li><code>View &#x26; Edit</code></li></ul><ul><li><code>Admin</code></li></ul>                                                                                                    |

You can add multiple rows for Devtron app permission.

Once you have finished assigning the appropriate permissions for the groups, Click **Save**.

### Jobs

In `Jobs` option, you can provide access to a group to manage permission for jobs created using Devtron.

Provide the information in the following fields:

![](https://devtron-public-asset.s3.us-east-2.amazonaws.com/images/global-configurations/permission-group/permission-groups-jobs-v2.jpg)

| Dropdown        | Description                                                                                                                                                                                                                                                                                |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Project**     | <p>Select a project from the drop-down list to which you want to give permission to the group. You can select only one project at a time.<br>Note: If you want to select more than one project, then click <code>Add row</code>.<br></p>                                                   |
| **Job Name**    | <p>Select the specific job name or all jobs from the drop-down list.<br>Note: If you select <code>All Jobs</code> option, then the user gets access to all the current jobs including any new job which gets associated with the project later.<br></p>                                    |
| **Workflow**    | <p>Select the specific workflow or all workflows from the drop-down list.<br>Note: If you select <code>All Workflows</code> option, then the user gets access to all the current workflows including any new workflow which gets associated with the project later.<br></p>                |
| **Environment** | <p>Select the specific environment or all environments from the drop-down list.<br>Note: If you select <code>All environments</code> option, then the user gets access to all the current environments including any new environment which gets associated with the project later.<br></p> |
| **Role**        | <p>Select one of the <a href="permission-groups.md#role-based-access-levels">roles</a> to which you want to give permission to the user:</p><ul><li><code>View only</code></li></ul><ul><li><code>Run job</code></li></ul><ul><li><code>Admin</code></li></ul>                             |

You can add multiple rows for `Jobs` permission.

Once you have finished assigning the appropriate permissions for the groups, Click **Save**.

### Kubernetes Resources Permissions

In `Kubernetes Resources` option, you can provide permission to view, inspect, manage, and delete resources in your clusters from [Kubernetes Resource Browser](../../usage/resource-browser/) page in Devtron. You can also create resources from the `Kubernetes Resource Browser` page.

{% hint style="info" %}
Only super admin users will be able to see `Kubernetes Resources` tab and provide permission to other users to access `Resource Browser`.
{% endhint %}

To provide Kubernetes resource permission, click `Add permission`.

![](https://devtron-public-asset.s3.us-east-2.amazonaws.com/images/global-configurations/permission-group/kubernetes-resources-permission-group-v2.jpg)

On the `Kubernetes resource permission`, provide the information in the following fields:

![](https://devtron-public-asset.s3.us-east-2.amazonaws.com/images/global-configurations/user-access/user-permission/kubernetes-resources-permission-page-v2.jpg)

| Dropdown          | Description                                                                                                                                                                                                                                     |
| ----------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Cluster**       | <p>Select a cluster from the drop-down list to which you want to give permission to the user. You can select only one cluster at a time.<br>Note: To add another cluster, then click <code>Add another</code>.<br></p>                          |
| **Namespace**     | Select the namespace from the drop-down list.                                                                                                                                                                                                   |
| **API Group**     | Select the specific API group or `All API groups` from the drop-down list corresponding to the K8s resource.                                                                                                                                    |
| **Kind**          | Select the kind or `All kind` from the drop-down list corresponding to the K8s resource.                                                                                                                                                        |
| **Resource name** | Select the resource name or `All resources` from the drop-down list to which you want to give permission to the user.                                                                                                                           |
| **Role**          | <p>Select one of the <a href="permission-groups.md#role-based-access-levels">roles</a> to which you want to give permission to the user and click <code>Done</code>:</p><ul><li><code>View</code></li></ul><ul><li><code>Admin</code></li></ul> |

You can add multiple rows for Kubernetes resource permission.

Once you have finished assigning the appropriate permissions for the groups, Click **Save**.

### Chart Group Permissions

In `Chart group permission` option, you can manage the access of groups for Chart Groups in your project.

{% hint style="info" %}
The `Chart group permission` option will be available only if you install [CI/CD integration](../../usage/integrations/build-and-deploy-ci-cd.md).
{% endhint %}

![](https://devtron-public-asset.s3.us-east-2.amazonaws.com/images/global-configurations/permission-group/permission-group-chart-v2.jpg)

{% hint style="info" %}
You can only give users the ability to `create` or `edit`, not both.
{% endhint %}

| Action | Permissions                                                                                                                                                                                                                                                                                                                                               |
| ------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| View   | Enable `View` to view chart groups only.                                                                                                                                                                                                                                                                                                                  |
| Create | Enable `Create` if you want the users to create, view, edit or delete the chart groups.                                                                                                                                                                                                                                                                   |
| Edit   | <ul><li><strong>Deny</strong>: Select <code>Deny</code> option from the drop-down list to restrict the users to edit the chart groups.</li><li><strong>Specific chart groups</strong>: Select the <code>Specific Charts Groups</code> option from the drop-down list and then select the chart group for which you want to allow users to edit.</li></ul> |

Click **Save** once you have configured all the required permissions for the groups.

### Edit Permissions Groups

You can edit the permission groups by clicking the `downward arrow.`

![](https://devtron-public-asset.s3.us-east-2.amazonaws.com/images/global-configurations/permission-group/edit-permission-group.jpg)

Edit the permission group.

![](https://devtron-public-asset.s3.us-east-2.amazonaws.com/images/global-configurations/permission-group/save-permission-group.jpg)

Once you are done editing the permission group, click **Save**.

If you want to delete the groups with particular permission group, click **Delete**.
