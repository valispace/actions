# Valispace commit-changes Action

This action extends [EndBug/add-and-commit](https://github.com/EndBug/add-and-commit) by also managing branch protection rules, while also simplifying the inputs and outputs.

**NOTE**

A [Personal Access Token (PAT)](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) is required to manage the protected branch rules!

_This is **not** intended to replace the original action!_

## Usage

<!-- start usage -->
```yaml
uses: valispace/actions/commit-changes@master
with:
  # The account owner of the repository (the name is not case sensitive).
  # Required: true
  # Default: ''
  repository-owner: '${{ github.repository_owner }}'
  # The name of the repository (the name is not case sensitive).
  # Required: true
  # Default: ''
  repository-name: '${{ github.event.repository.name }}'
  # The branch where to commit.
  # Required: true
  # Default: ''
  branch-name: '${{ github.ref_name }}'
  # The commit author (one of `github_actions`, `github_actor`, `user_info`).
  # Required: true
  # Default: ''
  commit-author: 'github_actions'
  # The commit message.
  # Required: true
  # Default: ''
  commit-message: 'Valispace build 1.0.0'
  # The token to manage the protected branch rules.
  # Required: true
  # Default: ''
  protected-branch-token: '${{ secrets.REPO_ADMIN_TOKEN }}'
```
<!-- end usage -->

## Outputs

The following outputs are available:
|Name|Type|Description|
|---|---|---|
|committed|Boolean|Whether the action has created a commit|
|commit-long-sha|String|The complete SHA of the commit that has been created|
|commit-sha|String|The short SHA of the commit that has been created|
|pushed|Boolean|Whether the action has pushed to the remote|

## License

The scripts and documentation in this project are released under the [MIT License](LICENSE)
