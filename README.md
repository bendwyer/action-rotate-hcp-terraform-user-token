<!-- action-docs-all source="action.yml" project="bendwyer/action-rotate-hcp-terraform-user-token" version="v1" -->
## action-rotate-hcp-terraform-user-token

### Description

Rotates a HCP Terraform user token stored as a secret in a GitHub repository.

### Inputs

| name | description | required | default |
| --- | --- | --- | --- |
| `github_token` | <p>GitHub token used for writing the HCP Terraform user token to the repository secret store. Requires the repository permission secrets:write. The repository permission environments:write is optional.</p> | `true` | `""` |
| `github_secrets_name` | <p>Name of the secret in the repository secret store where the token will be written.</p> | `false` | `HCP_TERRAFORM_USER_TOKEN` |
| `hcp_terraform_user_token` | <p>HCP Terraform user token to be rotated. This token must already exist and be saved as a repository secret before running this action.</p> | `true` | `""` |
| `hcp_terraform_user_token_description` | <p>Description for the HCP Terraform user token. Must be the same for the original and new tokens.</p> | `false` | `github-token` |
| `hcp_terraform_user_token_expiration` | <p>Time in days when the HCP Terraform user token will expire.</p> | `false` | `30` |


### Runs

This action is a `composite` action.

### Usage

```yaml
- uses: bendwyer/action-rotate-hcp-terraform-user-token@v1
  with:
    github_token:
    # GitHub token used for writing the HCP Terraform user token to the repository secret store. Requires the repository permission secrets:write. The repository permission environments:write is optional.
    #
    # Required: true
    # Default: ""

    github_secrets_name:
    # Name of the secret in the repository secret store where the token will be written.
    #
    # Required: false
    # Default: HCP_TERRAFORM_USER_TOKEN

    hcp_terraform_user_token:
    # HCP Terraform user token to be rotated. This token must already exist and be saved as a repository secret before running this action.
    #
    # Required: true
    # Default: ""

    hcp_terraform_user_token_description:
    # Description for the HCP Terraform user token. Must be the same for the original and new tokens.
    #
    # Required: false
    # Default: github-token

    hcp_terraform_user_token_expiration:
    # Time in days when the HCP Terraform user token will expire.
    #
    # Required: false
    # Default: 30
```
<!-- action-docs-all source="action.yml" project="bendwyer/action-rotate-hcp-terraform-user-token" version="v1" -->

Resources
---------

- [Changing Passwords and Updating Tokens Outside of the Terraform Cloud and Terraform Enterprise UI](https://support.hashicorp.com/hc/en-us/articles/4402342106003-Changing-Passwords-and-Updating-Tokens-Outside-of-the-Terraform-Cloud-and-Terraform-Enterprise-UI)
