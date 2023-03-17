# Valispace update-valiadmin-services Action

This action updates ValiAdmin with the given build of self deployed services.

## Usage

<!-- start usage -->
```yaml
uses: valispace/actions/update-valiadmin-services@master
with:
  # The name of the service.
  # Required: true
  # Default: ''
  service_type: 'vali-engine'
  # The environment of the service.
  # Required: true
  # Default: ''
  environment: 'develop'
  # The build version.
  # Required: true
  # Default: ''
  version: '1.0.0'
  # The endpoint of the service.
  # Required: true
  # Default: ''
  domain: 'vali-engine.develop.services.valispace.com'
  # The access token of the given service.
  # Required: true
  # Default: ''
  access_token: 'XXXX'
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
