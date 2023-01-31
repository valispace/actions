# Valispace docker-push-image Action

This action extends [docker/build-push-action](https://github.com/docker/build-push-action) by focusing in just pushing a Docker image to a Docker registry, while also simplifying the inputs.

_This is **not** intended to replace the original action!_

## Usage

<!-- start usage -->
```yaml
uses: valispace/actions/docker-push-image@master
with:
  # Build's context is the set of files located in the specified PATH or URL.
  # Required: false
  # Default: '.'
  context: '.'
  # Path to the Dockerfile.
  # Required: false
  # Default: 'Dockerfile'
  dockerfile: 'backend/vali/Dockerfile'
  # Server address of Docker registry (if not set it will default to Docker Hub).
  # Required: false
  # Default: ''
  registry: 'ghcr.io'
  # Username used to log against the Docker registry.
  # Required: false
  # Default: '${{ github.repository_owner }}'
  username: '${{ github.repository_owner }}'
  # Password or personal access token used to log against the Docker registry.
  # Required: false
  # Default: '${{ github.token }}'
  password: '${{ secrets.GITHUB_TOKEN }}'
  # Log out from the Docker registry at the end of a job.
  # Required: false
  # Default: 'true'
  logout: true
  # Specifies whether the given registry is ECR (`auto`, `true` or `false`).
  # Required: false
  # Default: 'auto'
  ecr: 'auto'
  # List of metadata for an image.
  # Required: false
  # Default: ''
  labels: |
    version=1.0.0
  # List of tags.
  # Required: false
  # Default: ''
  tags: |
    ghcr.io/valispace/vali:develop
```
<!-- end usage -->

## License

The scripts and documentation in this project are released under the [MIT License](LICENSE)
