# Valispace docker-build-push Action

This action extends [docker/build-push-action](https://github.com/docker/build-push-action) by combining it with action [docker/login-action](https://github.com/docker/login-action) and simplifying the inputs and outputs.

_This is **not** intended to replace the original actions!_

## Usage

<!-- start usage -->
```yaml
uses: valispace/actions/docker-build-push@master
with:
  # Push is a shorthand for --output=type=registry'
  # Required: false
  # Default: 'false'
  push: true
  # Server address of Docker registry (if not set it will default to GitHub Container Registry).
  # Required: false
  # Default: 'ghcr.io'
  registry: 'ghcr.io'
  # Username used to log against the Docker registry.
  # Required: false
  # Default: '${{ github.repository_owner }}'
  username: '${{ github.repository_owner }}'
  # Password or personal access token used to log against the Docker registry.
  # Required: false
  # Default: '${{ env.GITHUB_TOKEN }}'
  password: '${{ env.GITHUB_TOKEN }}'
  # Log out from the Docker registry at the end of a job.
  # Required: false
  # Default: 'true'
  logout: true
  # Specifies whether the given registry is ECR (`auto`, `true` or `false`).
  # Required: false
  # Default: 'auto'
  ecr: 'auto'
  # List of tags.
  # Required: false
  # Default: 'latest'
  tags: |
    valispace/vali:latest
    valispace/vali:1.0.0
  # List of metadata for an image.
  # Required: false
  # Default: ''
  labels: 'version=1.0.0'
  # Path to the Dockerfile.
  # Required: false
  # Default: ''
  file: 'Dockerfile'
  # Build's context is the set of files located in the specified PATH or URL.
  # Required: false
  # Default: '.'
  context: '.'
```
<!-- end usage -->

## Outputs

The following outputs are available:
|Name|Type|Description|
|---|---|---|
|imageid|String|Image ID|
|digest|String|Image digest|
|metadata|JSON|Build result metadata|

## License

The scripts and documentation in this project are released under the [MIT License](LICENSE)
