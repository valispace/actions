# Valispace aws-ecs-update-service Action

This action updates the service on AWS ECS and forces a new deployment

## Usage

<!-- start usage -->
```yaml
uses: valispace/actions/aws-ecs-update-service@master
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
  # The AWS ECS cluster.
  # Required: true
  # Default: ''
  ecs-cluster: 'services-cluster-prod'
  # The AWS ECS service.
  # Required: true
  # Default: ''
  ecs-service: 'valiengine'
```
<!-- end usage -->

## License

The scripts and documentation in this project are released under the [MIT License](LICENSE)
