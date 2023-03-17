# Valispace aws-build-push-image Action

This action build and push a image to a given AWS ECR repository

## Usage

<!-- start usage -->
```yaml
uses: valispace/actions/aws-build-push-image@master
with:
  # The AWS Secret Access Key.
  # Required: true
  # Default: ''
  aws-secret-access-key: '${{ secrets.AWS_SECRET_ACCESS_KEY }}'
  # The AWS Access Key ID.
  # Required: true
  # Default: ''
  aws-access-key-id: '${{ secrets.AWS_ACCESS_KEY_ID }}'
  # The AWS Region (e.g. `eu-central-1`).
  # Required: false
  # Default: 'eu-central-1'
  aws-region: 'eu-central-1'
  # The AWS ECR Repository (e.g. `vali-engine`).
  # Required: true
  # Default: ''
  aws-repository: 'vali-engine'
  # The dockerfile location.
  # Required: true
  # Default: ''
  dockerfile-path:
  # The build version.
  # Required: true
  # Default: ''
  version: 'valiengine'
  # The environment associated with the version.
  # Required: true
  # Default: ''
  environment: 'prod'
```
<!-- end usage -->

## License

The scripts and documentation in this project are released under the [MIT License](LICENSE)
