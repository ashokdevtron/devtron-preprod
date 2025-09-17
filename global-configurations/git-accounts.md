# Git Accounts

Git Accounts allow you to connect your code source with Devtron. You will be able to use these git accounts to build the code using the CI pipeline.

## Add Git Account

To add git account, go to the `Git accounts` section of `Global Configurations`. Click **Add git account**.

![](https://devtron-public-asset.s3.us-east-2.amazonaws.com/images/global-configurations/git-accounts/git-accounts.jpg)

Provide the information in the following fields to add your git account:

| Field                 | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `Name`                | <p>Provide a name to your Git provider.<br>Note: This name will be available on the App Configuration > <a href="../usage/applications/creating-application/git-material.md">Git repository</a> drop-down list.<br></p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| `Git host`            | <p>It is the git provider on which corresponding application git repository is hosted.<br>Note: By default, <code>Bitbucket</code> and <code>GitHub</code> are available in the drop-down list. You can add many as you want by clicking <code>[+ Add Git Host]</code>.<br></p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| `URL`                 | <p>Provide the Git host <code>URL</code>.<br>As an example: <a href="https://github.com">https://github.com</a> for GitHub, <a href="https://gitlab.com">https://gitlab.com</a> for GitLab etc.</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `Authentication Type` | <p>Devtron supports three types of authentications:</p><ul><li><strong>User auth:</strong> If you select <code>User auth</code> as an authentication type, then you must provide the <code>Username</code> and <code>Password</code>or <code>Auth token</code> for the authentication of your version control account.</li></ul><ul><li><strong>Anonymous:</strong> If you select <code>Anonymous</code> as an authentication type, then you do not need to provide the <code>Username</code> and <code>Password</code>.<br>Note: If authentication type is set as <code>Anonymous</code>, only public git repository will be accessible.</li></ul><ul><li><strong>SSH Key:</strong> If you choose <code>SSH Key</code> as an authentication type, then you must provide the <code>Private SSH Key</code> corresponding to the public key added in your version control account.</li></ul> |

## Update Git Account

To update the git account:

1. Click the git account which you want to update.
2. Update the required changes.
3. Click `Update` to save the changes.

Updates can only be made within one Authentication type or one protocol type, i.e. HTTPS (Anonymous or User Auth) & SSH. You can update from `Anonymous` to `User Auth` & vice versa, but not from `Anonymous` or `User Auth` to `SSH` and vice versa.

![](https://devtron-public-asset.s3.us-east-2.amazonaws.com/images/global-configurations/git-accounts/update-git-accounts.jpg)

Note:

* You can enable or disable a git account. Enabled git accounts will be available on the App Configuration > [Git repository](../usage/applications/creating-application/git-material.md).

![](https://devtron-public-asset.s3.us-east-2.amazonaws.com/images/global-configurations/git-accounts/git-account-enable-disable.jpg)
