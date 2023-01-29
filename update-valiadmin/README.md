# Valispace update-valiadmin Action

This action updates ValiAdmin with the given build.

## Usage

<!-- start usage -->
```yaml
uses: valispace/actions/update-valiadmin@master
with:
  # The name of the repository (the name is not case sensitive).
  # Required: true
  # Default: ''
  repository-name: 'valispace'
  # The branch to update.
  # Required: true
  # Default: ''
  branch-name: 'develop'
  # The build version.
  # Required: true
  # Default: ''
  version: '1.0.0'
  # The ValiAdmin (staging) access token.
  # Required: true
  # Default: ''
  valiadmin-staging-token: '${{ secrets.VALIADMIN_STAGING_TOKEN }}'
  # The ValiAdmin (prod) access token.
  # Required: true
  # Default: ''
  valiadmin-master-token: '${{ secrets.VALIADMIN_MASTER_TOKEN }}'
```
<!-- end usage -->

## License

The scripts and documentation in this project are released under the [MIT License](LICENSE)
